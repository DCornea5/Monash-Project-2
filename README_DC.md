# Monash-Project-2
MONU Project2

## Project subject  

### QS World University Rankings 2017-2022  

Dataset source https://www.kaggle.com/prasertk/qs-world-university-rankings-2021?select=QS+World+University+Rankings+combined.csv.<br />


##### Team members

Anh Huong<br />
Daniela Cornea<br />
Aravind Sama<br />
Mino Peric<br />

## Project Proposal


Review, analyse and group the QS World University Rankings by using CSV files available on Kaggle, https://www.kaggle.com/prasertk/qs-world-university-rankings-2021?select=QS+World+University+Rankings+combined.csv.  
The selected dataset contains a number of six CSV files, one for each year, plus one for the combined data. The database to be created will include information from at least four files, being for ranking for the period 2019 - 2022.  
The database is a relational database being structures in tables for universities and ranking. 
QS World University Rankings is published annualy by UK company Quacquarelli Symonds (QS) that analysis higher education institutions around the world and publish the results, in the current form, since 2004. The list contains more then 1000 universities and it is a trusted reference top universities in the world. 

Suggested files allocation<br />
Anh Huong QS World University Rankings 2022.csv<br />
Daniela Cornea QS World University Rankings 2021.csv<br />
Aravind Sama QS World University Rankings 2020.csv<br />
Mino Peric QS World University Rankings 2019.csv<br />

#### Project plan and development<br />

With a quick analysis in Excel by using Pivot Table, it can be noted that the number of universities varies from a year to another one and there are missing values in different columns such as rank, city and score. 

Project plan and development:

Each member of the team works with at least one CSV file, drop the logo and link columns, and retain year, rank_display, university, score, country, city and region.

Check the files for missing values by using different methods such as heatmap visualisation.

![Missing_Values_2021_count](Output_DC/visualizing_missing_data_2021_count.png)  

![Missing_Values_2021](Output_DC/visualizing_missing_values_2021.png)  

##### Extract

The original data was formatted in CSV files by year with specific columns for university, rank_display, score, country, region, city, logo and link. The datatype differs, and for 2021, as an example, the year column has datatype integer, the score is float and all the other columns are object.
The original data contains numbers or ranges for rank_display and some rows contain special characters such as "-" and "+".
Each file has around 1000 rows, representing universities around the world.

##### Transform

Data cleaning required for the files included:   
- replace NAN values in the "score" column with zero,   
- rename "rank_display" column as "rank"and replace NAN values with zero, retain the lower rank, drop unnecesary information such as special characters, remove "=" sing that appears in front of the rank in some rows.

##### Load

Database UniRankingDC created in PGAdmin includes 3 tables: cities, universities and uni_rank.
Cities has three headings: city, country and region. This table is to be updated with teh cities where universities are located. Some universities offer study programs in more then one city.
The headings for universities table are university, country, city and region. This table is intended to be a list with all universities.
The table uni_rank has the following headings university, year, rank, score. This table contains information about ranking by year. It permits analysing and plotting data for a londer period.






