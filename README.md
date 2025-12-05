ngage2Value Project Summary 

The Engage2Value project develops a two-step machine learning approach to predict customer purchase value using transaction and customer-level features. The workflow begins with loading and inspecting the training and test datasets, followed by cleaning and preprocessing. Redundant and non-informative columns—such as constant-value and high-null features—are removed to reduce noise. High-cardinality categorical variables are dropped to avoid excessive dimensionality.

A preprocessing pipeline is built to handle missing values, scale numeric attributes, and encode categorical fields. The preprocessed data is then split into training and validation sets. Because the problem involves predicting both whether a purchase occurs and how much is spent, the solution adopts a cascaded model structure.

First, a classifier is trained to identify purchase vs. non-purchase outcomes. Various metrics and validation checks ensure the model generalizes well. Next, a regression model is trained only on records where purchases occur, allowing the prediction of actual purchase values with better precision.

For the final prediction pipeline, the classifier is applied to the full test dataset to flag likely purchase events. For customers predicted to purchase, the regression model estimates the purchase value; all others are assigned zero. The outputs are combined to generate a complete prediction set, which is formatted into a submission file matching the challenge’s required structure.

This modular design—clean preprocessing, two-stage modeling, and structured prediction—makes the approach scalable, interpretable, and well-suited for real-world customer value forecasting.
