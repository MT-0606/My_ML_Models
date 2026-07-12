# Yelp Rating Linear Regression Project

This project explores whether Yelp business ratings can be predicted from business, review, user, tip, photo, and check-in data. The main goal is to practice the full linear regression workflow: preparing data, selecting usable numeric features, examining correlations, training models, evaluating `R^2`, and interpreting which features are most useful for predicting Yelp `stars`.

## Project Overview

The raw data comes from several Yelp JSON files. Each file describes a different part of the Yelp ecosystem, including businesses, reviews, users, tips, photos, and check-ins. These tables can be combined because they share the `business_id` column, which identifies the business connected to each row of information.

After merging the data, columns that were not directly useful for linear regression were removed. This included identifiers, raw text fields, location labels, timestamps, dictionaries, and other non-numeric values such as `address`, `business_id`, `categories`, `city`, `hours`, `name`, `postal_code`, `state`, and `time`.

## Workflow

1. Loaded the Yelp datasets.
2. Inspected the columns and ranges of values.
3. Merged the datasets using `business_id`.
4. Removed features that were not continuous or binary.
5. Checked for missing values.
6. Calculated correlations with Yelp rating, stored in `stars`.
7. Built linear regression models with different feature subsets.
8. Compared model performance using training and test `R^2` scores.
9. Interpreted which features were most important to Yelp rating predictions.

## Key Correlations

The feature with the strongest positive correlation to Yelp rating was `average_review_sentiment`. This makes intuitive sense: businesses with more positive review language tend to have higher star ratings.

The strongest negative relationship was with `average_review_length`. One possible interpretation is that longer reviews may be more likely to include detailed complaints or mixed experiences, though correlation alone does not prove causation.

The three features most closely examined against `stars` were:

- `average_review_sentiment`
- `average_review_length`
- `average_review_age`

## Model Results

The first model used only `average_review_length` and `average_review_age`. Its scores were:

- Training `R^2`: `0.0825`
- Test `R^2`: `0.0808`

These values are very low, meaning those two features alone explain only a small amount of the variation in Yelp ratings.

Additional feature sets performed better:

| Feature Set | Training R^2 | Test R^2 |
| --- | ---: | ---: |
| Sentiment only | 0.6119 | 0.6114 |
| Binary features | 0.0122 | 0.0101 |
| Numeric features | 0.6735 | 0.6713 |
| All features | 0.6808 | 0.6782 |
| Custom feature subset | 0.6616 | 0.6595 |

The best-performing model used all available numeric and binary features, though the numeric-only and custom-subset models also performed fairly well. Across the stronger models, `average_review_sentiment` remained the most important predictor.

## Interpretation

The results suggest that review sentiment is much more predictive of Yelp rating than basic binary business attributes such as whether a business has Wi-Fi, accepts credit cards, or has bike parking. Binary features alone performed poorly, with a test `R^2` close to zero.

The all-feature model performed best, but its advantage over the numeric-feature model was small. This suggests that most of the predictive signal came from numeric review, user, and business engagement features rather than binary business attributes.

## Linear Regression Questions

**What feature do the DataFrames have in common?**

The DataFrames share the `business_id` feature. This makes sense because reviews, tips, photos, check-ins, and business records all need to connect back to a specific business.

**What features best correlate, both positively and negatively, with Yelp rating?**

`average_review_sentiment` had the strongest positive correlation with Yelp rating. `average_review_length` had one of the strongest negative correlations.

**Why does `average_review_sentiment` correlate so well with Yelp rating?**

The sentiment of review text is closely related to the star rating because both measure customer experience. If reviewers describe a restaurant positively, they are also more likely to give it a higher rating.

**What do the first model's R^2 values say about the model?**

The first model's `R^2` values were approximately `0.08` for both training and testing. Because these scores are much closer to `0` than to `1`, the model does not explain much of the variation in Yelp ratings. The selected features, `average_review_length` and `average_review_age`, are not strong enough on their own to predict ratings effectively.

**Does the predicted-vs-actual plot follow the line `y = x`?**

No. A perfect model would have predictions close to the line `y = x`, where predicted ratings match actual ratings. The model's predictions do not follow that pattern closely, which confirms that the two-feature model is weak. The spread of errors also suggests the model is not consistently accurate across the rating range.

**How does changing feature sets affect the model's R^2 value?**

Changing the feature set has a major effect on model performance. Binary features alone produce very low `R^2` values, while sentiment and numeric features perform much better. The all-feature model has the highest test score, but the improvement over the numeric-feature model is modest.

## Conclusion

The most important takeaway is that Yelp ratings are strongly connected to review sentiment. Models that include `average_review_sentiment` perform much better than models that rely only on business attributes or simple review metadata. Linear regression can capture some of the relationship between Yelp features and star ratings, but the model is still imperfect and leaves room for more advanced feature engineering or nonlinear modeling.
