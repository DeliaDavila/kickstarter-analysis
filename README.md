# An Analysis of Kickstarter Campaigns
## Overview of Project
From Kickstarter funding campaign data, I will answer two questions:
1. When do successful projects tend to launch?
2. What goal amounts have tended to be successful?

### Purpose
Louise, the purpose of this project is to make your Kickstarter for your play *Fever* as successful as possible. To do this, I analyzed Kickstarter data to determine some best practices for launching a Kickstarter.

## Analysis and Challenges
To help answer your questions, I created two visualizations. The first graph *Theater Outcomes by Launch Date* tells you what month is best to launch a successful theater Kickstarter campaign. The second graph *Outcomes based on Goals* helps you set your goal by looking at what goal amounts have tended to be successful. 

### Analysis of Outcomes Based on Launch Date
To create this graph, I created a pivot table with months of the year are shown in rows and outcomes in columns. 

![PivotTable](https://github.com/DeliaDavila/kickstarter-analysis/blob/main/Images/PivotTable.png)

At the top, two filters allow you to sort by parent category and years. For the launch date question, the category is "theater" and all years are included (no filter is set). This table shows how many campaigns were launched in each month of the year, with separate totals for different outcomes (successful, failed, canceled). 

![OutcomesTable](https://github.com/DeliaDavila/kickstarter-analysis/blob/main/Images/OutcomesTable.png)

From this pivot table, I created the graph *Theater Outcomes by Launch Date*. I'll list my conclusions in the Results section, but notice that successful campaigns have a distinct pattern of when the highest successful outcomes are launched.

![Theater_Outcomes_vs_Launch](https://github.com/DeliaDavila/kickstarter-analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals
To create the second graph *Outcomes based on Goals*, I created a table with projects separated into goal levels in the rows and columns for each outcome (successful, failed, canceled).

![OutcomesGoals](https://github.com/DeliaDavila/kickstarter-analysis/blob/main/Images/OutcomesGoals.png)

To populate the table, I limited the data in three ways to sort counts into columns and rows
- Subcategory "plays"
- By outcome (columns for: successful, failed, canceled) 
- By goal level (rows for: less than a thousand, 1-5 thousand, 5-10 thousand, etc.)

Here is a sample of the code used for the first funding level:

```
=COUNTIFS(Kickstarter!$F:$F,"successful", Kickstarter!$R:$R, "plays", Kickstarter!$D:$D,"<1000")
```

Once the successful, failed, and canceled numbers were organized into funding levels, I summed up the numbers to come up with total projects for each goal level. 

![TotalProjects](https://github.com/DeliaDavila/kickstarter-analysis/blob/main/Images/TotalProjects.png)

Using the outcome numbers in each column and the total, I calculated the percentage of outcomes in each goal level. 

![Percentages](https://github.com/DeliaDavila/kickstarter-analysis/blob/main/Images/Percentages.png)

From this data, I created the *Outcomes based on Goals* graph. 

![Outcomes_vs_Goals](https://github.com/DeliaDavila/kickstarter-analysis/blob/main/Resources/Outcomes_vs_Goals.png)

Again, see the Results section for my conclusions. But notice that, up until the goals go beyond $30,000, as the campaign goals increase, there are fewer Successful campaigns and more Failing ones. Before we discuss Results, I'll discuss some challenges.

### Challenges and Difficulties Encountered
One potential issue with *Theater Outcomes by Launch Date* would be drawing conclusions from just successful campaigns. Without the comparison of other outcomes, the successful projects might indicate overall numbers for each month. In other words, if most campaigns were launched in a month, that month would be more likely to have the most successful campaigns, as well as most of the failed and canceled ones. Adding the failed and canceled outcomes as additional lines shows that the pattern for those outcomes is not the same as the successful campaigns. This indicates that the pattern for successful outcomes is not only related to the total number of launches.

Another issue with *Theater Outcomes by Launch Date* is that results are for all campaigns related to theater. Different kinds of projects exist within that data so this graph alone doesn't give you a complete picture of campaigns just for plays. The “when to launch” question is best answered broadly, but for help determining how to set a funding goal, I limited the data for *Outcomes based on Goals* more so that you aren’t comparing a play launch to a project with a much larger scope, such as building a theater space. 

An issue with *Outcomes based on Goals* is that results are not consistent at higher funding levels. Larger projects may have more varied sources (planned giving, corporate gifts, or government grants), so the dataset might be missing information about other funding options at higher levels. For this reason, I limited my conclusion to funding goals below $30,000 because the data is clearer and more related to your project. Projects at lower levels are more likely to be funded by individual donors without prior planning, so you should make decisions based on lower levels if you have no additional funding commitments prior to starting the campaign.

## Results
Conducting analysis of the raw Kickstarter data, I was able to answer your two questions about how to structure a Kickstarter campaign. I also have sections to discuss limitations and make additional suggestions.

- Conclusions from *Theater Outcomes by Launch Date*
1. Theater projects launched in May have significantly more successful outcomes than failed outcomes. This is the best month to launch a campaign.
2. Theater projects launched in December have a much lower success rate. Avoid launching a campaign in December.

- Conclusion from *Outcomes based on Goals*
For smaller campaigns (goals under 30,000 dollars), the success rate declined and the failure rate increased as campaigns increased their goal amounts. From this, I suggest that you set your goal at the smallest amount possible for your budget.

- What are some limitations of this dataset?
The dataset is limited in some ways. One limit is that the data is only for Kickstarter, which is not the only means of crowdfunding a project. 

Another limit is that the data doesn’t contain information about how many people saw the campaign, merely how many people contributed. It’s not possible to determine directly how many people will need to see your campaign in order to reach enough backers for the project to be successful.

- Additional suggestions
To help you determine best practices for other aspects of your campaign, I suggest additional visualizations drawn from the data. 
1. A graph showing the average donation for successful and unsuccessful projects shown by goal level. This may help you decide what perk amounts work the best.
2. A graph showing number of backers of successful and unsuccessful projects at each goal level. This may help you estimate the reach you'll need for a campaign to succeed.
3. A graph showing what percent of successful projects exceeded their funding goal for each goal level. This might help you structure stretch goals.
