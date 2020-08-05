# NYPD-Officer-Complaints-Analysis
This project is based on a data set containing complaints filed against currently serving NYPD officers. The source is: https://www.propublica.org/datastore/dataset/civilian-complaints-against-new-york-city-police-officers

Each row of the data lists a complaint, and the columns include various details on officers (name, race, age, gender, month and year of incident, rank at the time of incident, current rank) and complainants (race, age, gender) as well as other details such as the reason why the officer made contact, the outcome of contact, and the findings of NYPD's Civilian Complaint Review Board (classified as Unsubstantiated, Exonerated, or one of the several variations of Substantiated with different punishments recommended). It's noteworthy that NYPD can choose to ignore the recommendations of the Board.

I assigned numerical values to ranks as per their hierarchical order in NYPD, and also to the findings of the Board (0 when the verdict was Unsubstantiated or Exonerated, and 1 when it was any variation of Substantiated). This allows for some interesting analyses.

The code is divided into 10 different parts/sections, each of which unearths interesting insights from the data. Some of those are mentioned below:

#### Part 1: Exploratory analyses 
1. The data has a total of 33358 complaints (rows) against 3996 unique officers, and the oldest complaint goes all the way back to 1985.
2. About 54% of complaints are against White officers, 27% against Hispanic officers and 14% against Black officers
3. Ignoring the NA values, about 59% of complaints are by Black people, 22% by Hispanic people and 9% by White people
4. 2/3rd complaints come against Police Officers - the lowest ranked in the NYPD hierarchy
5. The disciplinary board either exonerates or fails to substantiate complaint in 75% of cases

#### Part 2: How about White cops-Black people?
1. Somewhat counterintuitively, a White officer is not more likely than cops of other races to face a complaint by a Black person. White officers face 58.7% of their complaints from Black people, whereas the share of Black people in total complaints is 59.2%. This suggests that things wouldn't change much if there were only White officers in NYPD.
2. In fact, among officers of all races, Black officers are most likely to face a complaint by a Black person. This proportion is 66%.
3. Note: This statistic does NOT conclusively suggest that there is no racism by White officers against Black people (or that Black officers are especially harsh on Black people), since that would require data on the total number of contacts made by White (and Black) officers with Black people, among other things.
4. Looking at gender-wise breakup, female officers face 38.7% of complaints from women, and male officers face only 16% of complaints from women.

#### Part 3: Who are the most errant officers?
1. The top 100 officers - 2.5% of total - with most complaints against them make up 11% of the total complaints.
2. The interactive bubble chart provides details on each of these 100 officers.

#### Part 4: Does an officer's ethnicity impact how quickly (or slowly) the Board reaches a decision?
1. Histograms comparing officers of different shows that this isn't the case - the board reaches a decision on nearly all complaints within 20 months, regardless of the race of the officer

#### Part 5: Are the youth more likely to file a complaint?
1. Yes - a histogram shows that 60% complaints come from people between the ages of 14 and 34. Note that this could either be because the officers are more likely to commit abuses against the youth or because the youth are more likely to report abuses, or both.

#### Part 6: Does being found guilty of misconduct affect officers' promotion?
1. For an officer, "promotion" is calculated as the difference between the current rank and the rank at the time of the very first complaint against the officer.
2. The function takes in two inputs: year and rank, and draws a scatter plot of promotion vs average guilty score (calculated by assigning 0 to all complaints where the Board's verdict was unsubstantiated or exonerated and 1 where it was substantiated). 
3. The year input acts as the year in which officers faced their first complaint, and rank input acts as the rank of officer at the time of the first complaint. Controlling for year and rank allows an apples-to-apples comparison. For instance, it would not make a lot of sense to compare promotions of officers who faced their first complaint as Lieutenants in 2002, to those who faced their first complaint as Sergeants in 2007.
4. The scatteplot suggests that, for a certain year and rank, officers who get promoted higher have lower average guilty score (negative correlation). However, this isn't a strong correlation and I refrained from performing statistical tests because of too many unknowns.

#### Part 7: Visualize changes in ranks of each of the 3996 officers
1. I've drawn a Sankey diagram to show change between the current rank and the rank at the time of the first incident, for each unique officer.
2. The function takes in as input a certain year (the year in which officers faced their first complaint) and shows their current ranks. The interactive diagram displays the number of officers who got promoted between each pair of rankings, as well as their average guilty score. For instance, the group of officers who moved from being Police Officers in 2005 to Lieutenants now are plotted on this diagram, and their total number and guilty score can be seen by hovering over the diagram.

#### Part 8: Are Black people singled out for certain offences?
1. It's usually believed that officers are more likely to target Black people for offences such as Stop/Question/Frisk, Vehicle Stop and Check, Report of Disturbance/Noise among others. This doesn't seem to be the case looking at the data, although it's hard to make a conclusive comment because of a preponderance of NaN values for complainant's ethnicity in such offences.

#### Part 9: How often have cops been accused of chokehold/restricting breathing, and by which races?
1. 265 of 33358 complaints - less than 1% - pertain to chokehold or restricting breathing, and 61% of those are by Black People (their share in overall complaints is 59.2%)

#### Part 10: Does the board's decision depend on the race of the complainant and the officer?
1. Generally, the Board finds the officer guilty in 1/4 complaints. However, the ratio is 1/8 for American Indian officers (the sample size complaints against American Indian officers is just 32, compared to many more for officers of other ethnicities).
2. Similarly, the Board is significantly more likely determine guilt in complaints filed by American Indian complainants (again, much fewer number of complaints filed by this group).



Credits: https://towardsdatascience.com/data-visualization-with-bokeh-in-python-part-ii-interactions-a4cf994e2512 (was crucial to helping me make Bokeh plots)
