# Netflix_data_analysis


Exploratory data analysis of a 9,800+ movie dataset to uncover genre trends, popularity drivers, and rating patterns — framed as the kind of data-driven investigation a streaming platform's analytics team might run to inform content decisions.

## 📌 Project Overview

Netflix relies heavily on data to understand audience behavior and guide content strategy. This project simulates that kind of analysis: given a raw dataset of over 9,000 movies, the goal is to clean it, explore it, and answer a set of business-relevant questions using Python.

**Questions answered:**
1. What is the most frequent genre of movies in the dataset?
2. Which category has the highest votes in the `Vote_Average` column?
3. What movie got the highest popularity? What's its genre?
4. What movie got the lowest popularity? What's its genre?
5. Which year had the most filmed movies?

## 🗂️ Dataset

The dataset (`mymoviedb.csv`) contains **9,827 movies** with the following columns:

| Column | Description |
|---|---|
| `Release_Date` | Original release date |
| `Title` | Movie title |
| `Overview` | Short plot summary |
| `Popularity` | Popularity score |
| `Vote_Count` | Number of votes received |
| `Vote_Average` | Average rating |
| `Original_Language` | Language code |
| `Genre` | Comma-separated genre list |
| `Poster_Url` | Link to poster image |

## 🧹 Data Cleaning & Preprocessing

- Checked for and confirmed **no missing values or duplicates** in the raw data.
- Converted `Release_Date` to datetime and extracted the **release year**.
- Dropped columns not useful for analysis: `Overview`, `Original_Language`, `Poster_Url`.
- **Binned `Vote_Average`** into four categories (`not popular`, `below_avg`, `average`, `popular`) using quartile-based cutoffs, via a reusable `categorize_col()` function.
- **Split and exploded the `Genre` column** so each row represents a single movie–genre pair, then cast it to a `category` dtype for efficient analysis.

## 📊 Visualizations

Built with `Seaborn` and `Matplotlib`:
- Genre distribution (count plot)
- Vote average category distribution
- Release year distribution (histogram)

## ✅ Key Findings

- **Most frequent genre:** Drama — appearing in over **14%** of entries across 19 genres.
- **Highest-rated genre by popularity:** Drama again leads, making up **18.5%** of movies in the "popular" vote category (25.5% of the dataset falls into that category overall).
- **Highest popularity:** *Spider-Man: No Way Home* (Action, Adventure, Science Fiction).
- **Lowest popularity:** *The United States, Thread* (Music, Drama, War, Sci-Fi, History).
- **Most active release year:** **2020** had the highest number of filmed movies in the dataset.

## 🛠️ Tech Stack

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## 🚀 Getting Started

```bash
git clone https://github.com/Cocobot01/Netflix_data_analysis.git
cd Netflix_data_analysis
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook Netflex_dataanalysis.ipynb
```

## 📁 Repository Structure

```
├── mymoviedb.csv                  # Raw dataset
├── Netflex_dataanalysis.ipynb     # Full analysis notebook
└── README.md
```

## 🔮 Future Improvements

- Add genre-level popularity/vote correlation analysis
- Explore trends over time (genre popularity by decade)
- Build an interactive dashboard (e.g., Streamlit) for filtering by genre/year
