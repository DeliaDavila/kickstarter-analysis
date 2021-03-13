# An Analysis of Kickstarter Campaigns
## Overview of Project
I have raw data on Kickstarter funding campaigns that includes descriptive information such as location or type of project, as well as information about the size or success of campaigns. Using this data, I will answer two questions:
1. When do successful projects tend to launch?
2. What goal amounts have tended to be successful?

### Purpose
Louise, the purpose of this project is to help you use Kickstarter for funding your play *Fever*. To do this, I will analyze Kickstarter data to determine if there are best practices for launching a Kickstarter.
## Analysis and Challenges
To help answer your questions from raw Kickstarter data, I created two visualizations. The first graph *Theater Outcomes by Launch Date* answers the question of what month would be best to launch a successful theater Kickstarter campaign. The second graph *Outcomes based on Goals* helps you determine what goal amounts have tended to be successful. 
### Analysis of Outcomes Based on Launch Date
![Theater_Outcomes_vs_Launch](https://github.com/DeliaDavila/kickstarter-analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)

To create this graph, I created a pivot table with two filters at the top that allow the data to be sorted by parent category and years. Months of the year are shown in rows and outcomes in columns. 
![PivotTable](https://github.com/DeliaDavila/kickstarter-analysis/blob/main/Images/Theater_Outcomes_vs_Launch.png)

For the launch date question, the category is set to theater and the years is left unfiltered. This creates a table showing how many campaigns were launched in each month of the year, with separate totals for different outcomes (successful, failed, canceled). 
![OutcomesTable](https://github.com/DeliaDavila/kickstarter-analysis/blob/main/Images/Theater_Outcomes_vs_Launch.png)

From this pivot table, I created a line graph. successful campaigns have a distinct pattern of highest successful outcomes in May and lowest successful outcomes in The graph shows that December.
### Analysis of Outcomes Based on Goals
![Outcomes_vs_Goals](https://github.com/DeliaDavila/kickstarter-analysis/blob/main/Resources/Outcomes_vs_Goals.png)

To create this visualization, I first created a table that separated projects into goal levels in the rows and outcomes (successful, failed, canceled) in columns.

![OutcomesGoals](https://github.com/DeliaDavila/kickstarter-analysis/blob/main/Images/Theater_Outcomes_vs_Launch.png)

To populate these columns, I limited the data in three ways to sort counts into columns and rows
- Subcategory "plays"
- By outcome (columns for: successful, failed, canceled) 
- By goal level (rows for: less than a thousand, 1-5 thousand, 5-10 thousand, etc.)

Here is a sample of the code used for the data:
'''
=COUNTIFS(Kickstarter!$F:$F,"successful", Kickstarter!$R:$R, "plays", Kickstarter!$D:$D,"<1000")
'''
Once the successful, failed, and canceled numbers were organized into funding levels, I summed up the numbers to come up with total projects for each goal level. 
![TotalProjects](https://github.com/DeliaDavila/kickstarter-analysis/blob/main/Images/Theater_Outcomes_vs_Launch.png)

Using the outcome numbers in each column and the total, I calculated the percentage of outcomes in each goal level. 
![Percentages](https://github.com/DeliaDavila/kickstarter-analysis/blob/main/Images/Theater_Outcomes_vs_Launch.png)

From this data, I created the line graph. The graph shows a decline in Successful outcomes and an increase in Failing outcomes as the campaign goals increase, up until the goals go beyond $30,000. After this point, the relationships are less clear.
### Challenges and Difficulties Encountered
One potential issue with *Theater Outcomes by Launch Date* would be drawing conclusions from just the successful campaigns. Without the comparison of other outcomes, the successful projects might indicate overall numbers for each month. Adding the failed and canceled outcomes as additional lines allows me to show that the pattern for successful outcomes is just for successful campaigns, not all campaigns regardless of outcome.
Another issue with *Theater Outcomes by Launch Date* is that it shows results for all campaigns related to theater. Different kinds of projects exist within that data so just this graph alone won’t give a good picture of campaigns for plays. The “when to launch” question is best answered broadly, but for help determining how to set a funding goal, we’ll need to limit the data more so that you aren’t comparing a play launch to very different projects that might have much larger goals, such as building a theater space. 
An issue with *Outcomes based on Goals* is that results are not consistent at higher funding levels. Larger projects may have more varied sources (planned giving, corporate gifts, or government grants), so the data set might be missing information about other funding options at higher levels. For this reason, my conclusion is stated for funding goals below $30,000 because a conclusion is more evident. Projects at lower levels are more likely to be funded by individual donors without prior planning, so you should make decisions based on those lower levels if you have no additional commitments prior to starting the campaign.
## Results
Conducting analysis of the raw Kickstarter data, I was able to answer your two questions about how to structure a Kickstarter campaign. The conclusions are presented in sections below for each of the visualizations prepared. I have also made some additional suggestions following the conclusions.
- What are two conclusions you can draw about the Outcomes based on Launch Date?
1. Theater projects launched in May have significantly more successful outcomes than failed outcomes. 
2. Theater projects launched in December have a much lower success rate.
- What can you conclude about the Outcomes based on Goals?
For smaller campaigns (goals under 30,000 dollars), the success rate declined and the failure rate increased as campaigns increased their goal amounts. I suggest that you set your goal at the smallest amount possible for your budget.
- What are some limitations of this dataset?
The dataset is limited in some ways. One limit is that the data is only for Kickstarter, which is not the only means of crowdfunding a project. Another limit is that the data doesn’t contain information about how many people saw the campaign, merely how many people contributed. It’s not possible to determine directly how many people will need to see your campaign in order to reach enough backers for the project to be successful.
- What are some other possible tables and/or graphs that we could create?
To help you understand the situation more, I would suggest additional visualizations drawn from the data. 
1. A graph showing the average donation for successful and unsuccessful projects shown by goal level. This would help you determine what target gift amounts to set perks for.
2. A graph showing number of backers of successful and unsuccessful projects at each goal level. This would give you a sense of how many people you’ll need to reach for her campaign to succeed.
3. A graph showing what percent of successful projects exceeded their funding goal for each goal level. This would give you more information to help with budgeting.
