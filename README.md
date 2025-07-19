## Box Office Breakdown: Data-Driven Insights for Smarter Movie Production

## Overview
The project Box Office Breakdown leverages data-driven analysis to provide actionable insights for smarter movie production decisions. It is designed to guide a new film studio, helping identify the key factors that drive box office success in today's highly competitive entertainment industry.

## Business Problem
With the surge of original content production by major entertainment companies, our organization plans to enter the movie industry by launching a new film studio. However, as newcomers, we face a significant knowledge gap in understanding the factors that contribute to box office success.

This project analyzes current industry trends to identify the types of movies that perform best financially. Our ultimate goal is to deliver data-driven, actionable recommendations to guide the studio's decisions on the types of films to produce and invest in.

Key Business Questions:
•	Are certain movie directors more likely to generate higher box office revenue?
•	Which genres tend to receive higher audience and critics ratings?
•	Is there a correlation between production budget and worldwide gross revenue?
•	Which original languages are more popular in screening in box office?

## Data Understanding and Analysis
The dataset was compiled from multiple reputable and diverse sources:
•	Box Office Mojo
•	IM.Db (SQLite database)
•	Rotten Tomatoes
•	TMDb Movies
•	The TN Movies Budgets
•	Rotten Tomatoe critic reviews
•	Rotten_Tomatoes_Movies

Key Notes
• Rotten Tomatoes Dataset Replacement: The original Rotten Tomatoes datasets lacked the audience ratings and critic ratings, making them unusable for merging. We replaced them with a more complete version from Kaggle.
• Exclusion of Box Office Mojo & RT Critic Reviews: The Box Office Mojo dataset was excluded due to overlap with the more complete TN Movies Budgets dataset. Similarly, RT Critic Reviews were excluded as the required ratings were already available in the Rotten Tomatoes Movies Info dataset.

## Data Description & Preparation
The primary focus of the analysis is to identify meaningful trends across production budgets, gross earnings, and audience ratings. These insights will support strategic decision-making for the new movie studio, enabling it to identify profitable genres and themes. By aligning content production with market demand and audience preferences, the studio can optimize its investment and increase the likelihood of producing successful original video content.

We loaded and explored the datasets using Python’s pandas library, leveraging functions like .info(), .describe(), and .isnull().sum() to assess data structure, data types, summary statistics, and missing values.

For advanced data profiling and cleaning, we also utilized:
• Data Wrangler for efficient data wrangling and profiling.
• SQLite Viewer for interactive exploration of database files.

After thorough discussion of the datasets, we carefully evaluated the available columns. Based on importance to our project goals and quality, we decided on a final set of columns that would be most effective for a meaningful analysis:

1. From rotten_tomatoes: genres, tomatometer_rating, audience_rating. These columns help us evaluate which movie genres tend to receive the highest critical and audience ratings.

2. From tmdb: language, popularity. These attributes allow us to investigate how a film's language impacts its popularity and, by extension, potential profitability

3. From tn_movie_budgets: production_budget, worldwide_gross. These financial figures are crucial for establishing the existence of relationship between production budgets and worldwide gross revenue.

4. From im.db: Extracting and joining data across the directors, persons, and movie_basics tables. This allows us to match each director with the correct movie title, enabling the analysis of which directors tend to deliver high foreign box office success.

Visualizations Utilized:
•	Horizontal & Vertical Bar Plots
•	Pie Chart
•	Scatter Plots

## Summary & Recommendations
1.  Focus on English-language productions: English (en) remains the dominant and most commercially successful original language in the global box office market.

2. Partner with proven directors: Collaborate with high-revenue directors such as Anthony and Joe Russo. Additionally, exploring partnerships with successful directors like Pierre Coffin, Christopher Nolan, and Joss Whedon may further improve the likelihood of commercial success due to their consistent box office performance.

3. Invest strategically in production budgets: The analysis shows a positive correlation between higher production budgets and higher worldwide gross revenues. While higher budgets don’t guarantee success, they generally correlate with stronger financial performance.

## Conclusion
By integrating these findings — prioritizing high-performing directors, producing content in English, aligning budgets to project scale, and focusing on quality — the studio is well-positioned to make informed, data-driven decisions that increase the likelihood of box office success and long-term sustainability.