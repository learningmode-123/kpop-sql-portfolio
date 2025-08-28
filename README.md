Welcome to my first data analysis\!  
Let’s start with something fun: KPOP\!\!\!

**Project: K-pop Song Rankings (2010–2023)**

**Goal:** Explore kpop ranking trends using SQL.  
**Dataset:** Kaggle \- Kpop songs rankings ([https://shorturl.at/IIrLQ](https://shorturl.at/IIrLQ))

**Questions answered:**

Basic

1. How many songs are in the dataset?  
2. How many unique artists are there?  
3. What are the top 10 songs with the highest ranking scores?

Intermediate

4. Which artist has the most songs in the dataset?  
5. What’s the average score of each artist?  
6. Which year had the most new songs entering the chart?

Advanced

7. Which artist had the **most weeks at \#1**?  
8. Trend analysis: Has the **average song score** increased or decreased over the years?

**Example Query:**

SELECT COUNT(song\_title)

from kpop\_rankings1;

**Key Insights:**

1. IU is the artist with the most number 1 songs in the dataset, followed by New Jeans and BTS.   
2. 2011 was the year with more new songs entering the chart, while 2018 was the year with the least amount of new songs entering the chart.  
3. The average rank has increased over the years, which means that the score has decreased. Since the highest score is 1 and the lowest is 200\. If more songs are getting lower scores, it means that a few songs are dominating the charts, so competition is increasing over time. According to the table, the change happened between 2018 and 2019\. In 2018, [**BTS hits No. 1**](https://www.billboard.com/pro/bts-first-k-pop-act-hit-no-1-artist-100-chart/) on *Billboard*‘s [**Artist 100**](https://www.billboard.com/charts/artist-100/) chart, making the group the first Korean artist to ever do so. This fast popularization of Kpop outside of Korea through BTS could be pointed as a propeller of competition among kpop groups. 

TIPS:  
Since the characters are in korean, I had to save the .csv as UTF-8 using the following in psql: \\copy kpop\_rankings1 FROM '/path/to/file’sname.csv' WITH (FORMAT csv, HEADER true, ENCODING 'UTF8');  
This way there wouldn’t be errors while reading the names. 

