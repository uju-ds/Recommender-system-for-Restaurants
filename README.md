# Recommender-system-for-Restaurants

### Step involved in this project

#### step1: Data Preparation:
1. Import and read the data 
2. view the range of the ratings
3. pivot the data to get it into a user-item matrix format
4. Imputing values for the NAN Values
5. check the number of rows and columns in the data
#### step 2: Collaborative Filtering: Recommend Restaurants to a New User
###### a. Fit an initial TruncatedSVD model with all the components on centered data
  1.  center the data
  2.  fit a TruncatedSVD model with 127 components
  3.  view the cumulative explained variance ratios
  4.  plot the cumulative explained variance ratios
##### b. Update the model to have 50 components
  1. fit a TruncatedSVD model with 50 components
  2. view the cumulative explained variance ratios
##### c. Introduce a New User for recommendation prediction using the fitted model
  1. view only the restaurants that the new user rated
  2. import and read in the restaurants details (second tab of spreadsheet)
##### d. Recommend Restaurants to the New User
  1. fill nan values with the mean rating
  2. center the new_user data
  3. transform the user into the latent space
  4. reconstruct the user-item matrix for the user
  5. view the shape of the output (1 user x 127 predicted ratings)
  6. make restaurant recommendations for the new user
  7. sort the recommendations to get the best 10
  8. combine the predicted ratings and restaurant details tables
#### step 3: Content-Based Filtering: Suggest Similar Restaurants to a Restaurant
##### a. Prep the data to contain only numeric values
   - turn the cuisine, price and franchise columns of the restaurant details data into numeric columns
   - turn cuisine into dummy variables
   - turn franchise into an indicator
   - combine them into a single dataframe
##### b. Calculate the cosine similarities between rows
   - find the most similar restuarants to KFC for someone that likes KFC
   - find the details of those restaurants by merging the outcome of the recommendation with the restaurant details
