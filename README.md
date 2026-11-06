# Netflix Movies and TV Shows: Independent Data Exploration

## Project Overview

This project explores a dataset of Netflix movies and TV shows to better

understand the composition and characteristics of the Netflix content catalog.

The dataset contains approximately 8,800 titles and includes information such

as content type, title, director, cast, country, date added, release year,

audience rating, duration, genre, and description.

The goal of this project was to apply an end-to-end data analysis process,

including data exploration, cleaning, missing-value analysis, outlier detection,

statistical analysis, and visualization, to identify meaningful patterns and

communicate actionable insights.

### Research Questions

The analysis was designed to answer the following questions:

1. What proportion of the Netflix catalog consists of movies versus TV shows?

2. How has the number of titles added to Netflix changed over time?

3. Which countries contribute the most content?

4. Which genres are most frequently represented?

5. Which audience ratings are most common?

6. What does the distribution of movie duration look like?

7. Are unusual movie durations legitimate observations or potential data issues?

8. What relationship exists between a title's release year and the year it was

   added to Netflix?

---

## Dataset

The Netflix Movies and TV Shows dataset was obtained from Kaggle.

The original dataset contains approximately:

- **8,800 titles**

- **12 original columns**

- Both **Movies** and **TV Shows**

- Content from multiple countries

- Release years spanning several decades

### Important Dataset Fields

| Field | Description |

|---|---|

| `show_id` | Unique identifier for each title |

| `type` | Movie or TV Show |

| `title` | Title of the content |

| `director` | Director |

| `cast` | Featured cast |

| `country` | Country or countries associated with the title |

| `date_added` | Date the title was added to Netflix |

| `release_year` | Original release year |

| `rating` | Audience/content rating |

| `duration` | Movie duration or number of TV seasons |

| `listed_in` | Genre/category information |

| `description` | Short description of the title |

---

## Tools and Technologies

The project was completed using:

- Python

- Google Colab

- Pandas

- NumPy

- Matplotlib

- Seaborn

- Jupyter Notebook

- GitHub

---

## Analysis Process

### 1. Initial Data Exploration

The first step was to understand the structure and quality of the dataset.

The analysis included:

- Reviewing the dataset dimensions

- Inspecting column names and data types

- Examining sample records

- Calculating descriptive statistics

- Checking for duplicate records

- Identifying unique values

- Measuring missing values

This step helped determine which variables required cleaning or transformation

before analysis.

---

### 2. Missing-Value Analysis

Missing values were evaluated by calculating both the number and percentage

of missing observations in each column.

Missing data was concentrated mainly in descriptive fields such as:

- Director

- Cast

- Country

Records were not automatically removed simply because these fields were

missing. Removing them would also eliminate useful information about release

year, genre, content type, rating, and duration.

Where appropriate, missing categorical values were labeled as `Unknown`.

---

### 3. Data Cleaning

Several transformations were performed to prepare the data for analysis.

These included:

- Standardizing column names

- Removing leading and trailing whitespace

- Checking and removing duplicate records

- Handling missing categorical values

- Converting `date_added` to a datetime data type

- Extracting the year and month a title was added

- Converting movie duration into numerical minutes

- Converting TV show duration into number of seasons

- Creating a primary country field

- Creating a primary genre field

- Calculating the age of content when it was added to Netflix

Movies and TV shows were given separate duration variables because movie

duration is measured in minutes while TV show duration is measured in seasons.

---

### 4. Outlier Analysis

Movie duration was examined for potential outliers using the

**Interquartile Range (IQR) method**.

The IQR was calculated as:

`IQR = Q3 - Q1`

Potential outliers were identified using:

`Lower Bound = Q1 - 1.5 × IQR`

`Upper Bound = Q3 + 1.5 × IQR`

Movies outside these boundaries were flagged as potential outliers.

These observations were **not automatically removed**.

Extremely short or long movies may represent legitimate content such as:

- Short films

- Documentaries

- Specials

- Concert films

- Extended features

Therefore, the outliers were retained unless there was evidence that the

underlying record was incorrect.

---

### 5. Statistical Analysis

Descriptive statistics were calculated for several important variables,

including:

- Release year

- Movie duration

- Number of TV show seasons

- Content age when added to Netflix

Both mean and median values were considered when analyzing movie duration.

The median was especially useful because it is less sensitive to unusually

short or long movies.

---

## Data Visualizations

The project uses several visualization techniques to communicate the major

findings.

Visualizations include:

1. Missing values by column

2. Movie duration boxplot and outlier analysis

3. Movies versus TV shows

4. Titles added to Netflix over time

5. Top countries represented in the catalog

6. Most common genres

7. Audience rating distribution

8. Movie duration distribution

9. Release year versus year added to Netflix

Different chart types, including bar charts, line charts, histograms,

boxplots, and scatterplots, were used depending on the analytical question.

---

## Key Conclusions

### 1. Movies Make Up the Majority of the Catalog

Movies represent approximately **70% of titles**, while TV shows account

for approximately **30%**.

This indicates that the catalog represented in the dataset is substantially

more movie-heavy.

However, this should **not** be interpreted as evidence that Netflix users

prefer movies. The dataset describes catalog availability rather than

viewer behavior.

---

### 2. Netflix Expanded Its Catalog Rapidly

The number of titles added to Netflix increased substantially during the

later years represented in the dataset.

Catalog additions accelerated particularly during the period from

approximately 2016 through 2019.

The final year in the dataset should be interpreted cautiously because

it represents only a partial year of observations.

---

### 3. Netflix Has a Global Catalog, but Content Is Concentrated

Content in the dataset comes from many different countries, demonstrating

the international nature of the Netflix catalog.

The United States and India are among the largest contributors.

However, geographic interpretation requires caution because a single title

may be associated with multiple countries.

---

### 4. Certain Genres Are More Common

International movies, dramas, and comedies are among the most frequently

represented genre categories.

Because a single title may belong to several genres, genre counts represent

genre assignments rather than completely separate groups of titles.

---

### 5. Mature and Teenage Content Is Strongly Represented

Ratings such as `TV-MA` and `TV-14` appear frequently in the catalog.

This suggests that mature and teenage audience categories are strongly

represented in the dataset compared with several younger-audience

categories.

---

### 6. Movie Duration Contains Legitimate Outliers

The movie-duration analysis identified both unusually short and unusually

long titles.

Instead of automatically deleting these records, they were retained because

many represent potentially valid types of content.

This highlights an important data-cleaning principle:

> An unusual value is not necessarily an incorrect value.

---

### 7. Netflix Contains Both Recent and Older Content

Comparing original release year with the year a title was added to Netflix

shows that the catalog includes both:

- Recently released content

- Older library content added years after its original release

This demonstrates that the catalog represented in the dataset combines new

releases with historical content.

---

## Recommendations

Based on the analysis, several improvements could be made in future work.

### Analyze Movies and TV Shows Separately

Movie duration and TV show duration represent different concepts.

Movies should be analyzed using minutes, while TV shows should be analyzed

using seasons.

### Expand Multi-Valued Fields

Country and genre fields frequently contain multiple values.

Future analysis could split these values into separate records to provide a

more complete view of geographic and genre representation.

### Add Popularity or Engagement Data

This dataset explains **what content exists**, but not **what audiences watch**.

A stronger future analysis could combine this dataset with information such

as:

- IMDb ratings

- Rotten Tomatoes ratings

- Viewer popularity

- Netflix Top 10 data

- Audience engagement metrics

This would make it possible to investigate whether catalog composition

aligns with popularity or audience preference.

---

## Project Limitations

There are several important limitations to this analysis.

- The dataset represents a historical snapshot of the Netflix catalog.

- It should not be considered the current Netflix catalog.

- The dataset contains catalog metadata rather than viewing behavior.

- Several descriptive fields contain missing values.

- Individual titles can have multiple countries.

- Individual titles can belong to multiple genres.

- The final year represented in the dataset may be incomplete.

- Catalog availability does not necessarily indicate popularity.

These limitations are important when interpreting the findings.

---

## Repository Structure

A recommended project structure is:

    netflix-independent-data-exploration/

    │

    ├── Netflix_Independent_Data_Exploration.ipynb

    ├── Netflix_Data_Exploration_5_Minute_Presentation.pdf

    ├── README.md

    │

    └── data/

        ├── netflix_titles.csv

        └── netflix_titles_cleaned.csv

---

## How to Explore the Project

### 1. Open the Notebook

Open:

`Netflix_Independent_Data_Exploration.ipynb`

The notebook contains the complete analysis, including explanations,

Python code, statistical calculations, and visualizations.

### 2. Run the Notebook

The notebook can be opened using Google Colab.

Run the cells sequentially from the beginning so that all cleaned variables

and calculated fields are created before the visualization sections.

### 3. Review the Analysis

The notebook follows this analytical workflow:

    Raw Dataset

        ↓

    Initial Exploration

        ↓

    Missing-Value Analysis

        ↓

    Data Cleaning

        ↓

    Statistical Analysis

        ↓

    Outlier Detection

        ↓

    Visualization

        ↓

    Interpretation

        ↓

    Conclusions

### 4. Review the Presentation

The presentation provides a concise five-minute summary of the analysis and

highlights the most important visualizations, conclusions, and recommendations.

---

## Potential Future Analysis

This project could be expanded by investigating questions such as:

- Have movie genres changed over time?

- Which countries experienced the fastest growth in Netflix representation?

- Are certain genres associated with longer movie durations?

- Do audience ratings vary significantly by country?

- How quickly are newly released titles added to Netflix?

- Do highly rated titles have different characteristics from other titles?

- How does Netflix catalog composition compare with other streaming services?

Additional external datasets could also be joined to the Netflix catalog to

study popularity, ratings, awards, revenue, or audience engagement.

---

## Final Takeaway

This project demonstrates a complete exploratory data analysis workflow,

beginning with raw data and progressing through cleaning, statistical analysis,

outlier detection, visualization, and interpretation.

The analysis shows that the Netflix catalog represented in this dataset is

movie-heavy, internationally diverse but geographically concentrated, strongly

represented by mature and teenage content, and composed of both recent releases

and older library titles.

Most importantly, the analysis demonstrates the importance of distinguishing

between **catalog composition** and **audience behavior**. The dataset can

explain what Netflix made available, but additional data would be required to

determine what audiences actually preferred or watched.
