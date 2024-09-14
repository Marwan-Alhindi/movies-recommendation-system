Based on the files you provided, including the reports and implementation framework, here’s a detailed `README.md` file for your project:

---

# Slope One Predictors with Personalized Weighted Collaborative Filtering

## Overview

This project implements a recommendation system using **Slope One Predictors** for **Online Rating-Based Collaborative Filtering**. The focus is on enhancing the traditional Slope One method by introducing a **Personalized Weighted Slope One Scheme**, which leverages user similarity to improve recommendation accuracy. By incorporating **user similarity metrics** such as centered cosine similarity, the personalized scheme improves prediction performance, offering more accurate recommendations than the standard Weighted Slope One model.

### Key Features

1. **Slope One Algorithm**:
   - The Slope One algorithm predicts a user’s rating for an item based on the user’s previous ratings of other items and the collective ratings of other users. 
   - Slope One is easy to implement, efficient, and can handle dynamic updates efficiently, making it ideal for real-world applications.

2. **Weighted Slope One with Personalization**:
   - A modification of the Weighted Slope One scheme was implemented by introducing **user similarity** into the formula. This allows for personalized recommendations that take into account not only the item-to-item relationships but also the similarity between users.
   - **Centered Cosine Similarity** is used to compute how similar a user is to others, and this similarity weight is applied to the Slope One prediction to improve accuracy.

3. **Mathematical Framework**:
   - The project builds on the mathematical model presented in the paper “Slope One Predictors for Online Rating-Based Collaborative Filtering” by Daniel Lemire and Anna Maclachlan. 
   - The implementation follows a rigorous framework of matrix operations, leveraging the **exponential function** for similarity weighting and **user-item interaction matrices** for the prediction calculations.

### System Design

- **Personalized Weighted Slope One Formula**:
   - The personalized prediction for user \( u' \) on item \( j \) is computed using the weighted average of deviations between item ratings, adjusted for user similarity:
     \[
     P_{pwSl}(u')j = \frac{\sum_{i \in S(u') - \{j\}} ((dev_{j,i} + u'_{i}) \cdot c_{j,i})}{\sum_{i \in S(u') - \{j\}} c_{j,i}}
     \]
   - Where:
     - \( dev_{j,i} \): deviation between item \( j \) and item \( i \),
     - \( u'_i \): rating given by user \( u' \) to item \( i \),
     - \( c_{j,i} \): the number of users who have rated both items \( i \) and \( j \).

- **User Similarity Adjustment**:
   - The standard Slope One model is extended to include user similarity \( sim(u, u') \) in the weighted average. This adjustment accounts for how similar user \( u \) is to other users who have rated the same items.

### Tasks and Results

1. **Task 1: Algorithm Implementation**:
   - The **personalized weighted Slope One method** was implemented by combining Slope One with a user similarity measure.
   - Key steps included:
     - Calculating the average rating deviation between items.
     - Adjusting this deviation based on the similarity between users.
     - Making predictions based on the adjusted deviation values and item ratings.
   
2. **Task 2: Evaluation and Comparison**:
   - The personalized method was compared with the standard Weighted Slope One scheme and other baseline collaborative filtering methods like Pearson’s correlation.
   - The personalized model demonstrated improved accuracy, especially for sparse datasets where user similarities were more informative in guiding predictions.

3. **Task 3: Presentation**:
   - A presentation was created to explain the workings of both the Slope One and Weighted Slope One schemes, along with a discussion of how introducing user similarity impacts the performance of the personalized model.
   - An analysis was also done on the impact of varying the **lambda parameter** \( \lambda \), which controls the balance between standard deviation and user similarity in the prediction formula.

### Files in the Repository

- **`code.ipynb`**: Contains the Python implementation of the personalized weighted Slope One scheme.
- **`Slope_One_Predictors_Report.pdf`**: Detailed explanation of the Slope One methodology and its mathematical foundation.
- **`PDS_2310_Assignment_3_Updated.pdf`**: Report summarizing the implementation details, challenges, and performance evaluation of the model.
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

### Languages and Tools

- **Python**: For implementing the recommendation algorithm.
- **Pandas**: For data manipulation and matrix operations.
- **NumPy**: For numerical computations, including calculating deviations and similarities.
- **Jupyter Notebook**: For interactive development and testing of the algorithm.

---

Let me know if any changes are needed or if you want to add further details!
