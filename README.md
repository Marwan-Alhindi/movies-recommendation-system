### Languages and Tools

- **Python**: For implementing the recommendation algorithm.
- **Pandas**: For data manipulation and matrix operations.
- **NumPy**: For numerical computations, including calculating deviations and similarities.
- **Jupyter Notebook**: Development environment for interactive coding.

# Slope One Predictors with Personalized Weighted Collaborative Filtering

## Overview

This project implements a recommendation system using **Slope One Predictors** for **Online Rating-Based Collaborative Filtering**. The focus is on enhancing the traditional Slope One method by introducing a **Personalized Weighted Slope One Scheme**, which leverages user similarity to improve recommendation accuracy. By incorporating **user similarity metrics** such as centered cosine similarity, the personalized scheme offers more accurate recommendations than the standard Weighted Slope One model.

### Key Features

1. **Slope One Algorithm**:
   - The Slope One algorithm predicts a user’s rating for an item based on the user’s previous ratings of other items and the collective ratings of other users. 
   - Slope One is easy to implement, efficient, and can handle dynamic updates, making it ideal for real-world applications.

2. **Weighted Slope One with Personalization**:
   - A modification of the Weighted Slope One scheme was implemented by introducing **user similarity** into the calculation. This allows for personalized recommendations that take into account not only item-to-item relationships but also the similarity between users.
   - **Centered Cosine Similarity** is used to compute how similar a user is to others, and this similarity weight is applied to the Slope One prediction to improve accuracy.

3. **Mathematical Framework**:
   - The project builds on the mathematical model presented in the paper "Slope One Predictors for Online Rating-Based Collaborative Filtering" by Daniel Lemire and Anna Maclachlan. 
   - The implementation follows a rigorous framework of matrix operations, leveraging user-item interaction matrices for the prediction calculations.

### System Design

- **Personalized Weighted Slope One**:
   - This approach adjusts the standard Slope One prediction by considering how similar a user is to others who have rated the same items. The higher the similarity, the more influence that user's ratings will have on the prediction.

- **User Similarity Adjustment**:
   - User similarity, calculated using centered cosine similarity, enhances the Weighted Slope One model by giving more weight to ratings from users who are more similar to the active user. This allows for more personalized recommendations.

### Tasks and Results

1. **Task 1: Algorithm Implementation**:
   - The **Personalized Weighted Slope One method** was implemented by combining Slope One with a user similarity measure.
   - Key steps included:
     - Calculating the average rating deviation between items.
     - Adjusting this deviation based on the similarity between users.
     - Making predictions based on the adjusted deviation values and item ratings.
   
2. **Task 2: Evaluation and Comparison**:
   - The personalized method was compared with the standard Weighted Slope One scheme and other baseline collaborative filtering methods like Pearson’s correlation.
   - The personalized model demonstrated improved accuracy, especially for sparse datasets where user similarities were more informative in guiding predictions.

3. **Task 3: Presentation**:
   - A presentation was created to explain the workings of both the Slope One and Weighted Slope One schemes, along with a discussion of how introducing user similarity impacts the performance of the personalized model.
   - An analysis was done on how the **lambda parameter** affects the balance between the standard deviation and user similarity in the prediction process.

### Files in the Repository

- **`code.ipynb`**: Contains the Python implementation of the Personalized Weighted Slope One scheme.
- **`dataset.zip`**: Contains the datasets used for training and testing the recommendation system.

### How to Run the Project

1. **Set Up Jupyter Notebook**:
   - Install Jupyter Notebook using Anaconda or any preferred method.
   - Open `code.ipynb` and run the cells to execute the personalized weighted Slope One implementation.

2. **Data**:
   - The dataset is pre-loaded in the notebook. Follow the instructions in the notebook to run the algorithm on the provided training and test sets.

3. **Evaluation**:
   - The output will display predicted ratings for test users along with metrics like Mean Absolute Error (MAE) to compare the performance of different collaborative filtering models.

### Data Source

The dataset used for this project is based on a collaborative filtering dataset (such as MovieLens or EachMovie), containing user ratings for various items (e.g., movies). The dataset is pre-processed for use in the Slope One prediction algorithm.
