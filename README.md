
## GOOGLE PLAY STORE EXPLORATORY DATA ANALYSIS
An end-to-end Python data analytics project focused on cleaning, transforming, and analyzing over 10000 apps from the Google Play Store dataset using Pandas. The goal is to analyze the app market to understand category trends, pricing strategies, user ratings, and download patterns. These insights can help app developers align their products with current market demands.

---

## Tech Stack & Tools
* **Language:** Python
* **Libraries:** Pandas, NumPy
* **Visualization:** Matplotlib, Seaborn 
* **Environment:** Visual Studio Code 

---

## Data Cleaning and Preprocessing
Before analysis, the raw data was cleaned to ensure accuracy:
* **Missing Values:**  Handled null values in columns.

* **Data Type Conversion:** Converted `Reviews` to numeric, and stripped characters (like `+`, `,`, and `$`) from `Installs` and `Price` to turn them into numerical types.

* **`Size` Cleaning:** * Standardized the column by replacing "Varies with device" with NaN. Developed a data transformation pipeline using Python lambda functions to convert Megabytes (M) to Kilobytes by multiplying by 1,000, and stripped the k character from Kilobyte values, successfully casting the entire feature into a uniform numeric scale (KB).
  * Converting the final column to a clean float type.

  * **Missing Value Imputation:** Handled `Rating` and `Size` using **Grouped Median Imputation**. I didn't just fill it with a generic average of the whole dataset. 
  * Categorical Features `Type`, `Current Ver` and `Android Ver`: Filled null values using a **mode imputation (.mode()[0])** to maintain categorical consistency.

  * **Date Time Conversion:**
  * The **Last Updated** column originally had dates written as text strings (like "January 7, 2018"), which Python cannot use for timeline analysis.
  * I converted this column into a real computer-readable format using pd.to_datetime().
  * To make it easier to see trends, I extracted three separate columns from it:  `Day`,`Month` and `Year`.
  * Finally, I removed the old text-based column to keep the dataset clean and lightweight. 

* **Duplicates:** Identified and removed duplicate app entries to avoid skewed analysis.

* **Data Pipeline Storage:** Saved the fully processed dataframe into a clean, standalone file: `Data/google_playstore_cleaned.csv`.

---

## Repository Structure

* `/Data`: Original raw dataset (`googleplaystore.csv`) and cleaned dataset.
  (`google_playstore_cleaned. csv`)
* `/Images`: Contains visualizations generated using matplotlib and seaborn.
* `/Googleplaystore.ipynb`: Cleaned and analyzed Jupyter Notebook file.
* `/README.md`: Markdown page containing project details.
* `/Requirements.txt`: Contains List of libraries.

----

##  Key Insights & Analytical Findings
### 1. Distribution of Numeric Data

![Numeric Distribution](Images/numeric_distribution.png)

### 2. Distribution of Categorical Data

![Category Distribution](Images/category_distribution.png)


### 3. Top 10 App Categories

![Top App Categories](Images/top10_apps.png)
 

### 4. Category with Large number of installations

![Category with Large Installations](Images/large_installs.png)


### 5. Top 5 Apps in Popular Categories

![Top 5 Apps in Popular Categories](Images/popular_categories.png)


### 6. Correlation Analysis

![Correlation Analysis](Images/correlation_analysis.png)

### 7. Time Series Analysis

![Time Series Analysis](Images/Time_analysis.png)


