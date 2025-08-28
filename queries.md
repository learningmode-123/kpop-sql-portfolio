1. CREATE TABLE  
   

CREATE TABLE kpop\_rankings (  
    year INT,           \-- 2010 to 2023  
    week INT,           \-- 1 to 53  
    rank INT,           \-- 1 to 200  
    song\_title TEXT,    \-- title of the song  
    artist TEXT,        \-- artists, multiple separated by comma  
    album TEXT          \-- album name  
);

2. SAVE AS UTF-8  
    use `\copy` in `psql`:  
   `\copy kpop_rankings1 FROM '/path/to/kpop_rankings.csv' WITH (FORMAT csv, HEADER true, ENCODING 'UTF8');`  
   

RESULTS:

1. How many songs are in the dataset?

`SELECT COUNT(*) FROM kpop_rankings;`

2. How many unique artists are there?

`SELECT COUNT(DISTINCT artist) FROM kpop_rankings;`

3. What are the top 10 songs with the highest ranking scores?

`SELECT song_title, artist, year, week`  
`FROM kpop_rankings`  
`WHERE rank = 1`  
`ORDER BY year, week;`

### **Intermediate**

4. Which artist appears most frequently in the dataset?

`SELECT artist, COUNT(*) AS appearances`  
`FROM kpop_rankings`  
`GROUP BY artist`  
`ORDER BY appearances DESC`  
`LIMIT 10;`

5. What’s the average score of each artist?

`SELECT artist, AVG(rank) AS avg_rank`  
`FROM kpop_rankings`  
`GROUP BY artist`  
`ORDER BY avg_rank ASC`  
`LIMIT 10;`

### **Advanced**

6. Which year had the most new songs entering the chart?

`SELECT year, COUNT(*) AS num_number_ones`  
`FROM kpop_rankings`  
`WHERE rank = 1`  
`GROUP BY year`  
`ORDER BY year;`

7. Which artist had the **most weeks at \#1**?

`SELECT artist, COUNT(*) AS number_ones`  
`FROM kpop_rankings`  
`WHERE rank = 1`  
`GROUP BY artist`  
`ORDER BY number_ones DESC`  
`LIMIT 10;`

8.Trend analysis: Has the **average song score** increased or decreased over the years?

SELECT year, AVG(rank) AS avg\_rank

FROM kpop\_rankings

GROUP BY year

ORDER BY year;

