# Data Analysis and Sentiment Analysis

A Python-based data analysis project built around a book dataset collected from [Books to Scrape](https://books.toscrape.com/). The notebook demonstrates web scraping, exploratory data analysis (EDA), statistical analysis, data visualization, and sentiment analysis of book titles.

## Overview

The project is organized as a step-by-step analysis workflow:

1. **Web Scraping**
   - Scrapes book information from Books to Scrape.
   - Collects book titles, prices, and star ratings.
   - Automatically follows pagination to collect the full dataset.
   - Saves the resulting dataset as CSV and Excel files.

2. **Exploratory Data Analysis**
   - Examines dataset dimensions, columns, and data types.
   - Checks for missing values and duplicate records.
   - Calculates descriptive statistics.
   - Examines rating distributions and price distributions.
   - Creates price buckets for further analysis.

3. **Statistical Analysis**
   - Uses one-way ANOVA to examine whether book prices differ significantly across rating groups.
   - Calculates Pearson correlation between book price and star rating.
   - Compares mean, median, and standard deviation of prices across ratings.

4. **Data Visualization**
   - Creates charts for rating and price distributions.
   - Visualizes relationships between price, ratings, and other derived variables.
   - Saves visualization outputs as PNG files.

5. **Sentiment Analysis**
   - Applies **VADER** sentiment analysis to book titles.
   - Applies **TextBlob** sentiment analysis to book titles.
   - Compares the sentiment classifications produced by the two methods.
   - Examines sentiment in relation to book star ratings.
   - Identifies the most positive and negative book titles according to VADER.
   - Exports sentiment results to an Excel file.

## Dataset

The notebook scrapes the dataset directly from:

**Books to Scrape** — https://books.toscrape.com/

The resulting dataset contains **1,000 books** with the following initial fields:

- `Title` — Book title
- `Price (£)` — Book price in pounds
- `Rating (1-5)` — Star rating from 1 to 5

Additional columns are created during analysis, including price buckets and sentiment-related features.

## Key Results

The analysis in the notebook reports:

- **1,000 books** collected.
- No missing values in the original three fields.
- No duplicate rows in the scraped dataset.
- Mean book price: **£35.07**
- Mean star rating: **2.92**
- One-way ANOVA for price vs. rating: **p = 0.8330**
- Pearson correlation between price and rating: **r = 0.0282, p = 0.3736**
- VADER classified book titles as:
  - Neutral: **624**
  - Positive: **213**
  - Negative: **163**
- TextBlob classified book titles as:
  - Neutral: **694**
  - Positive: **192**
  - Negative: **114**
- VADER and TextBlob agreed on the sentiment classification of **66.2%** of titles.

The statistical results in the notebook indicate no statistically significant difference in mean book price across rating groups and no strong linear relationship between price and rating.

## Project Structure

```text
data-analysis/
├── Data_Analysis.ipynb
├── README.md
└── requirements.txt
```

The notebook also generates datasets and visualization files when executed, including:

```text
books_dataset.csv
books_dataset.xlsx
sentiment_results.xlsx
chart1_rating_distribution.png
chart2_price_distribution.png
sentiment_chart1_overview.png
sentiment_chart2_heatmap.png
sentiment_chart3_violin.png
```

These generated files do not need to be committed to GitHub unless you specifically want to showcase the outputs.

## Installation

Create and activate a virtual environment if desired, then install the required packages:

```bash
pip install -r requirements.txt
```

## Running the Notebook

The notebook was developed with a Python 3 / Google Colab workflow.

Open `Data_Analysis.ipynb` in:

- Google Colab
- Jupyter Notebook
- JupyterLab
- VS Code with Jupyter support

Run the cells from top to bottom because later analysis depends on the dataset generated during the earlier web-scraping stage.

## Notes

The web-scraping section accesses the public Books to Scrape demonstration website. Internet access is therefore required when running the scraping portion of the notebook.

The notebook also contains Google Colab-specific download functionality for exporting generated CSV and Excel files. These download commands are not required for the analysis itself.

## Technologies Used

- Python
- Pandas
- NumPy
- Requests
- BeautifulSoup
- Matplotlib
- Seaborn
- SciPy
- VADER Sentiment
- TextBlob
- Jupyter Notebook / Google Colab
