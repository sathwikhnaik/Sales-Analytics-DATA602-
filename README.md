# Sales-Analytics-DATA602

## A. Group Members
1. Sathwik Hanumanth Naik (121227638)
1. Indrayudd Roy Chowdhury (120633249)
1. Tyusha Sarawagi (121305473)
1. Abhay Shagoti (121101341)

## B. Dataset Information
**Dataset Name:** Video Game Sales<br>
**Dataset Source:** [Kaggle](https://www.kaggle.com/datasets/gregorut/videogamesales)

## C. Pre-processing Steps (Tentative)  
### 1. Handling Missing Values
  -  #### Missing Year Values
      - Impute the missing years based on similar games (e.g., using mean or median of the Year for games on the same platform or genre).
      - Remove rows with missing years if they represent a small fraction of the data.
    
  -  #### Missing Publisher Values
      - Impute missing publisher data using similar approaches or mark them as "Unknown".
   
### 2. Feature Encoding

- #### Categorical Encoding
    - **Platform, Genre, Publisher**: These categorical columns may need to be encoded for possible machine learning models.
      - **One-hot encoding**: We could convert these into binary vectors (e.g., `Platform_Wii`, `Genre_Sports`).
      - **Label encoding**: Another option is converting categories into integer values. This may be useful if there's a natural order or if a simpler approach is preferred.

   

### 3. Scaling:

- The sales figures (`NA_Sales`, `EU_Sales`, `JP_Sales`, `Other_Sales`, `Global_Sales`) are continuous values and could vary widely. Scaling can be important for certain models.We will tentatively **normalize** the data which scales it between [0,1].

### 4. Removing Redundant Features:

- We could tentatively remove redundant features like and `Rank` as they don't influence the sales of the video games. Additionally, `Global_Sales` is just the summation of sales in all the regions, so there's an argument for removing the feature as well, depending on the outcome we choose.

