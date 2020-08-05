# NYPD-Officer-Complaints-Analysis
This project is based on a data set containing complaints filed against currently serving NYPD officers. The source is: https://www.propublica.org/datastore/dataset/civilian-complaints-against-new-york-city-police-officers

Each row of the data lists a complaint, and the columns include various details on officers (name, race, age, gender, month and year of incident, rank at the time of incident, current rank) and complainants (race, age, gender) as well as other details such as reason why the officer made contact, the outcome of contact, and the findings of NYPD's Civilian Complaint Review Board (classified as Unsubstantiated/Exonerated/Substantiated). It's noteworthy that NYPD can choose to ignore the recommendations of the Board.

The code is divided into 10 different parts/sections, each of which unearths interesting insights from the data. Some of those are mentioned below:

### Part 1: Exploratory analyses 
1. The data has a total of 33358 complaints (rows) against 3996 unique officers, and the oldest complaint goes all the way back to 1985.
2. About 54% of complaints are against White officers, 27% against Hispanic officers and 14% against Black officers
3. Ignoring the NA values, about 59% of complaints are by Black people, 22% by Hispanic people and 9% by White people
4. 2/3rd complaints come against Police Officers - the lowest ranked in the NYPD hierarchy
5. The disciplinary board either exonerates or fails to substantiate complaint in 75% of cases

### Part 2: Do White cops disproportionately mistreat Black people?
1. Somewhat counterintuitively, data suggests that this isn't the case. White officers face 58.7% of complaints from Black people, whereas the share of Black people in total complaints is 59.2%.
2. In fact, among officers of all races, Black people file their highest share of complaints - 66% - against Black officers.
3. Looking at gender-wise breakup, female officers face 38.7% of complaints from women, and male officers face only 16% of complaints from women.

#### Part 3: Who are the most errant officers?
1. The top 100 officers - 2.5% of total - with most complaints against them make up 11% of the total complaints.
2. The interactive bubble chart provides details on each of these 100 officers.

#### Part 4: Does an officer's ethnicity impact how quickly (or slowly) the Board reaches a decision?
1. Histograms comparing officers of different shows that this isn't the case - the board reaches a decision on nearly all complaints within 20 months, regardless of the race of the officer

#### Part 5: Are the youth more likely to file a complaint?
1. Yes - a histogram shows that 60% complaints come from people between the ages of 14 and 34. Note that this could either be because the officers are more likely to commit abuses against the youth or because the youth are more likely to report abuses, or both.

#### Part 6: Visualize changes in ranks of each of the 3996 officers
1. I've drawn a Sankey diagram to show change between the current rank and the rank at the time of the first incident, for each unique officer. 
1. Nearly 50% of the officers who were Police Officers at the time of their first complaint, are still Police Officers (many of these could be young officers, so their 


Credits: 
