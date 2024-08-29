**Project Progress Documentation: Personal Health Plan for Managing Blood Pressure and Sugar Levels**

### 1. Problem Statement

**Title**: Personal Health Plan for Managing Blood Pressure and Sugar Levels

**Overview**:
Chronic conditions such as high blood pressure (BP) and diabetes can be managed significantly through personalized dietary plans. Given that diet plays a crucial role in controlling these conditions, a tailored approach can lead to more effective management and improved patient outcomes. For example, personalized diet plans can reduce hospitalization rates and improve overall quality of life.

**Objective**:
Develop a system that offers personalized diet suggestions based on user food preferences, health metrics, and disease levels. Similar to how Spotify recommends songs, this system will track BP and sugar levels, provide diet plans to manage these levels, offer timely medication reminders, and predict future health levels based on current data. The effectiveness of the diet suggestions will be evaluated based on user feedback and improvement in health metrics over time.

### 2. Background Research

**Research Conducted**:
Consulted with an expert in the field—an MBBS undergraduate student with knowledge of Blood Pressure and sugar Level management. This research provided insights into:
- How BP and sugar levels are influenced by diet
- Key dietary and external factors that affect BP and sugar levels
- Potential data requirements for machine learning models

**Details**:
Specific insights from the expert included the importance of sodium reduction in managing BP and the role of fiber in controlling sugar levels. Understanding these factors has guided the selection of features for the model.

**Data Preparation**:
Based on the research, predefined data columns necessary for the ML model were identified. Each column was selected based on its relevance to dietary management of BP and sugar levels, such as `SugarContent` for diabetes management and `Sodium` for BP control.

### 3. Data Collection and Preparation

**Initial Data Columns Identified**:
- BP_Level
- Sugar_Level
- Age
- Gender
- BMI
- Activity_Level
- Alcohol
- Smoke
- DishName
- MajorIngredients
- Calories
- Proteins
- Fat
- Carbs
- Fiber
- Sodium
- Potassium
- Cholesterol
- SugarContent
- DietaryInfo
- ServingSize
- MealType
- DishCategory
- SuitabilityScore

**Challenges and Solutions**:
- **Problem 1: Finding Data**
  - **Challenge**: Difficulty in finding a dataset with the required columns from existing sources like Kaggle.
  - **Solution**: Generated synthetic data to represent dishes with the necessary columns. Utilized synthetic data generation tools (LangChain and OpenAI’s GPT) to create approximately 100 dish records. This data was validated for relevance.

- **Problem 2: Imbalanced and Dirty Dataset**
  - **Challenge**: A part of the dataset from Kaggle contained imbalanced and messy data with approximately 0.5 million rows.
  - **Solution**: 
    - **Data Balancing**: Reduced dataset size from 0.5 million to 5,000 rows using train_test_split and RandomUnderSampler.
    - **Data Cleaning**: Visualized and verified data balance. Scaled columns like `Age` (converted age categories to a 0-100 scale). Reduced data based on the balance between 'Diabetes', 'HighBP', 'Sex', and 'Age'.

### 4. Data Integration and Feature Engineering

**Data Integration**:
Combined synthetic dish data with Kaggle dataset to enrich the information and make it more comprehensive.

**Custom Algorithm**:
Developed a custom algorithm to compute a new column, `SuitabilityScore`, based on the integrated data. This score helps in determining how suitable each dish is for managing BP and sugar levels.
