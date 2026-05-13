Avito Maroc Real Estate Scraping & Data Cleaning
Project Overview

This project collects apartment sale listings from Avito Maroc using Selenium, then cleans and preprocesses the dataset using Pandas.

The pipeline follows a simple data engineering architecture:

Bronze Layer → raw scraped data
Silver Layer → cleaned and transformed data

The project extracts:

Title
Price
City
Surface
Bedrooms
Bathrooms
Listing URL
Project Structure
avito/
│
├── clean/
│
├── data/
│   ├── bronze/
│   │   └── raw.csv
│   │
│   └── silver/
│       └── cleaned.csv
│
├── extract/
│   └── scraping.py
│
├── staging/
│
├── docker-compose.yml
├── dockerfile
├── README.md
└── requirements.txt
Technologies Used
Python
Selenium
Pandas
Matplotlib
Seaborn
ChromeDriver
Installation
1. Clone the repository
git clone 
cd avito
2. Create virtual environment
python -m venv venv

Activate environment:

Windows
venv\Scripts\activate
Linux / Mac
source venv/bin/activate
3. Install dependencies
pip install -r requirements.txt
Requirements

Example requirements.txt

pandas
selenium
matplotlib
seaborn
Scraping Process

The scraper uses Selenium to navigate through Avito Maroc apartment listings pages.

Filters Used
Apartments for sale
Minimum 1 room
Minimum 1 bathroom
Listings with price
Surface > 30m²
Data Collected
Column	Description
titre	Apartment title
prix	Apartment price
ville	City/location
surface	Apartment surface
chambres	Number of bedrooms
salle_de_bain	Number of bathrooms
lien	Listing URL
Run Scraper
python extract/scraping.py

The raw dataset will be saved in:

data/bronze/raw.csv
Data Cleaning

The notebook performs several preprocessing steps:

Cleaning Steps
Handle Missing Values
Missing surfaces replaced with median
Missing bedrooms/bathrooms replaced with median
Convert Data Types
Price converted to numeric
Bedrooms converted to integer
Bathrooms converted to integer
Surface converted to integer
Feature Engineering

New column created:

prix_m2 = prix / surface
Remove Duplicates
df.drop_duplicates(inplace=True)
Exploratory Data Analysis (EDA)

The notebook includes:

Dataset overview
Missing values analysis
Price distribution visualization
Skewness analysis
Outlier detection using IQR

Example:

sns.histplot(df["prix"], kde=True)
Output

Final cleaned dataset:

data/silver/cleaned.csv

Dataset columns:

Column	Type
titre	object
prix	int
ville	object
surface	int
chambres	int
salle_de_bain	int
lien	object
prix_m2	int
Future Improvements
Add PostgreSQL storage
Build Airflow pipeline
Add Docker automation
Scrape additional property types
Create Power BI dashboard
Add machine learning price prediction model
Author

Created by ouiam elkhalfi 
