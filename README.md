# Analyzing Kickstarter Plays Based on Launch Dates and Funding Goals in Excel
## Introduction
A client was close to funding a Kickstarter campaign for her play titled *Fever*. I was tasked with analyzing how different Kickstarter campaigns perform concerning the campaign's launch date and the campaign's funding goals. The project is aimed towards campaigns in the "theater/play" category to better assist my client with information that may enable full funding of her next Kickstarter campaign.
### Preprocessing
The provided Kickstarter data set required minimal cleaning. Firstly, the launch date was converted from the UNIX timestamp using a formula that calculates the days, seconds, minutes the timestamp conveys with respect to the epoch. The converted date is listed as “Date Created Conversion”. Afterwards, the “Category/Subcategory” column was separated by the “Text to Columns” button, putting "Category" in the "Parent Category" column and "Subcategory" in a "Subcategory" column. Lastly, the outcomes were separated by utilizing conditionals. Each outcome successful, failed, or canceled was assigned a color green, red, and yellow respectively.
### Challenges 
There were minimal cleaning tasks required. Considering the size of the data set, if the timestamps conversions were completed manually, it would be tedious and increase the probability of wrongly classifying when outcome occurred. 
## Analysis and Challenges
### Theater Outcomes by Launch Date
A pivot table is used to analyze outcomes based on launch date by filtering the parent category to theater. The outcomes successful, failed and canceled are in the columns. Each row is labeled with a month of the year. The total quantity of each outcome per month for all years are shown in the pivot table.  The line graph created from the pivot table data shows the outcomes over twelve months for the years ranging from 2009-2017.
### Theater Outcomes Vs Launch Date
<img width="426" alt="Theater_Outcomes_vs_Launch" src="https://user-images.githubusercontent.com/87162266/132107831-409a0433-5d43-4b2b-85dd-51da4c2f34ae.png">

### Challenges
For the month of October in the pivot table there is a missing value in the canceled column.  During the project the value was not omitted purposefully, thus allowing an inconclusive analysis of the canceled outcome. 
### Outcomes Based on Funding Goal
The table on the "Outcomes Based on Goals" sheet divides the goals of Kickstarters by the goal dollar-amount ranges in each row. The first three columns are tabulated with the COUNTIF function to filter the outcomes based on the row in which it corresponds. For example, the formula in cell C3 reads “=COUNTIF (Kickstarter!$D:$D,">=1000", Kickstarter!$F:$F,"Failed", Kickstarter!$D:$D,"<=4999", Kickstarter!$R:$R,"Plays").” The next column sums each project outcome within each dollar-amount range.  The following three columns are the percentages of each outcome with respect to the dollar-amount range totals. A line graph shows the percentage of each outcome across the goal funding ranges.
### Outcomes Vs. Goals
<img width="822" alt="Outcomes_vs_Goals" src="https://user-images.githubusercontent.com/87162266/132107762-4de36e88-fd00-4be6-b5c7-5e00e984d5e6.png">

### Challenges
Generating the correct COUNTIF function was a personal challenge. In my trials, the syntax for the function wasn’t calculating the amounts of each cell correctly. I didn't include an equal sign in front of my greater than sign. Once achieved more values were counted. That minor error changed the totals in column E and consequently, all the percentages were corrected. Overcoming the syntax error was necessary to successfully complete the analysis on Kickstarters by dollar-amounts goals. 
## Conclusion
### Theater Outcomes by Launch Dates
Theater Kickstarters launched in May and June are more likely to be successful than any month during the year. May and June are a high-volume time for starting a Kickstarter in general.  In contrast, launching a Kickstarter in December has close to a 50% chance of failing. The odds of a successful outcome are greater in late spring, early summer than in the winter.
### Outcomes Based on Funding Goals
Kickstarters with the goal of $45,000 or more are more likely to fail at meeting their goal. The Kickstarters that had the greatest likelihood to reach their goal were $4,999 or less.
### Limitations
In the data set, there were no theater Kickstarters canceled in October between 2009-2017. It is likely that data is missing due to an error. The likelihood is there was at least one canceled play in October from 2009-2017, so perhaps the sample size wasn’t large enough to accurately convey theater Kickstarters. Other limitations were due to the currency of each Kickstarter corresponding with their country of origin. The currency wasn’t converted into one currency. The goals will likely change with the conversion to one currency, limiting the assumptions made about the funding goal's effects on a Kickstarter's outcome.
### Reccomendations
To convey the pivot table data a 2D or 3D bar graph could be used to compare the categories side by side for each month. A bar graph would help compare the outcomes for different funding goal ranges in each category side by side.
## Resources
[Kickstarter](https://www.kickstarter.com/film?ref=section-homepage-nav-click-film)

[Microsoft Support](https://support.microsoft.com/en-us/office/countif-function-e0de10c6-f885-4e71-abb4-1f464816df34)
