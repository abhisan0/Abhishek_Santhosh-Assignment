My Report for Hyperspectral Assignment

## Preprocessing
- I loaded the data in Colab and dropped `hsi_id` since it’s just an ID.
- I scaled the features with `MinMaxScaler` to keep them between 0 and 1.
- I scaled the DON concentration with `RobustScaler` because some values might be extreme.
- This helps the model learn better.

## Dimensionality Reduction
- I used PCA to see the data in 2D. The first 2 parts explained 92.5% of the variance.
- I checked and found 4 parts explain 95%, so the data can be made smaller.
- The PCA plot showed some colors based on DON, but it’s not super clear.

## Model Training
- I used XGBoost because I saw it’s good for predictions like this.
- I picked 150 top features with `SelectKBest` using mutual information.
- I split the data into 80% training and 20% testing, then trained with settings I chose.

## Results
- MAE: 2098.51 (average mistake in predictions)
- RMSE: 5388.66 (another error number)
- R² Score: 0.896 (my model got 90% right, which is great!)
- The plot shows my predictions are pretty close to the real values.

## What I Learned and Ideas
- I’m happy with R² = 0.896, but the errors are still big. I’ll check the DON range to see if it’s normal.
- Maybe I could try PCA features instead of picking 150 to see if it’s better.
- I could try a neural network next time if I learn how to do it.