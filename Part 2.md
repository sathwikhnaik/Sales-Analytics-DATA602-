# Project Part 2

## 1. Target Outcome

The target outcome for our project is **global sales** of video games. However, since global sales are simply the sum of regional sales (NA_Sales, EU_Sales, JP_Sales, and other regions), we aim to explore the influence of individual regional sales on global sales. 

### Approach:
- Instead of using all regional sales columns (which would be redundant), we will use one regional sales column at a time to predict global sales.
- We'll build separate models for each region (e.g., using NA_Sales, EU_Sales, JP_Sales as inputs), keeping all other parameters constant.
- **Performance Analysis:** We will calculate the Pearson Correlation Coefficient (PCC) for each regional model to determine which region has the highest correlation with global sales. This will help us identify the most impactful region.

We will also remove irrelevant columns such as `Name` of the game, as they do not contribute directly to predicting sales outcomes.

## 2. Feature Engineering

We plan to perform several feature engineering tasks to enhance the performance of our models:

### One-Hot Encoding:
- **Publishers:** Video game publishers can have a significant impact on sales. We will apply one-hot encoding to the `Publisher` column, allowing the model to learn from the categorical data.
- **Consoles:** Since many games are released across multiple platforms, we will one-hot encode the `Platform` column. This will allow us to treat different gaming consoles as distinct features. We will then aggregate sales for games across platforms by summing the sales for each game across all platforms.

### Time-Based Features:
- **Decades Instead of Years:** Instead of using the exact year of release, which might introduce too much granularity, we will group games by their decade of release. For example, games released between 2000-2009 will be labeled as “2000s”. This feature will capture larger trends in gaming history and reduce potential noise from using individual years.

By performing these transformations, we expect to give the model a clearer and more structured view of the data, which could improve prediction accuracy.

## 3. Handling Imbalanced Data

As this is a regression problem (predicting continuous sales values), we do not need to oversample or undersample the data. Our concern lies more in the distribution of the sales figures.

### Dealing with Sales Distribution:
- **Log Transformation:** Video game sales often follow a skewed distribution with a few games selling extremely well, while the majority sell less. To mitigate the influence of extreme values, we will apply a log transformation to the `Global_Sales` column. This will reduce the impact of outliers and help the model generalize better across a wider range of sales figures.

### Algorithm Selection:
- We plan to use algorithms that are less sensitive to data imbalances, such as **Random Forests** and **Gradient Boosting**. These methods can handle variations in data distribution more robustly than simpler linear models.

