# Performing Analysis on Kickstarter Data to Uncover Trends

## Overview of Project
### Purpose of Project
In this project, I demonstrated my proficiency with various features in excel including: conditional formatting, debugging errors, VLOOKUPs, and creating interactive charts and graphs with pivot charts. To accomplish these goals, I was given a fictional situation and data set of several thousand crowdfunding projects. 
### Background of Project
Louise, an up-and-coming playwright, wants to start a crowd funding campaign to fund her play *FEVER* which she estimates will cost over $10,000. The following report highlights specfic factors that lead to a successful campaign.     

---
## Analysis and Challenges
### Analysis
I organized the data to see if the month the kickstarter launched could impact its success. First, I made the data more detailed by splitting the Category and Subcategory column into two distinct columns. This allowed me to view the wider category of theater and later the narrower subcategory plays. Next, I converted Unix timestamps to identify the launch date. For example, I turned the cell **1434931811** into **06/22/15** using the code =(((J2/60)/60)/24)+DATE(1970,1,1). Finally, I created a pivot table that filtered based on "Parent Category" and "Years." From that pivot table I created the line graph shown below. 

![Theater_Outcomes_vs_Launch](Theater_Outcomes_vs_Launch.png)

Based on the line graph above, I had the following takeways about theather campaigns:
* May, June, and July respectively had the highest number of successful campaigns. 
* October and May respectively had the highest number of failed campaigns.
* December had about as many successful campaigns as failed ones.
* In every month there were more successful than failed campagins. Generally, the successful and failed trend lines create the same shape and are similar to each other with the exception of May, October, and December. In May, the larger than average gap between successful and failed campaigns suggests a better chance for success. In October, the smaller than average gap between successful and failed campaigns suggests a better chance for failure. 


Next, I organized the data to see if funding goal could impact the kickstarter's success. First, I needed to count the number of successful, failed, and canceled plays by goal. To do this, I used the COUNTIFS formula. For example, to count the number of successful plays with a goal between 1,000 and 4,999 I wrote the formula =COUNTIFS('Raw Data'!$O:$O, "plays",'Raw Data'!$D:$D, ">=1000", 'Raw Data'!$D:$D, "<5000", 'Raw Data'!$F:$F, "successful"). Then, I converted the number of successful, failed, and cancled plays to a percentage to more accurately compare them. Using this information, I created the line graph shown below. 

![Outcomes_vs_Goals](Outcomes_vs_Goals.png)

Based on the line graph above, I had the following takeways about play campaigns:
* Because there are zero cancled plays, successful and failed campaigns are symetric about the 50% line. 
* Generally, the percentage of successfully funded plays decreases as the goal increase with the exception of 29,999 to 49,999. This exception is likely due to a smaller sample size of 11 or less. 
* Plays will a goal of less than 5,000 have a success rate 20 points higher than plays will a goal between 5,000 and 20,000. 


### Challenges 
One challenge I encountered in writing my countifs formula was ensuring that I only counted the *plays*. Initially, my formula =COUNTIFS('Raw Data'!$D:$D, ">=1000", 'Raw Data'!$D:$D, "<5000", 'Raw Data'!$F:$F, "successful") counted every subcategory so I had to add an additional criteria and changed my formula to =COUNTIFS('Raw Data'!$O:$O, "plays",'Raw Data'!$D:$D, ">=1000", 'Raw Data'!$D:$D, "<5000", 'Raw Data'!$F:$F, "successful"). 

---
## Results
### My Reccomendation 
According to the data, Louise play's with a funding goal of $10,000 should be launched in May, June, or July and avoid a launch in October or December. Her currently funding goal has a 54% successful rate. If she could cut costs in half, her success rate would increase to approximately 70%. 

### Limitations 
Many of the limitations of this dataset come from the donation collection. For example, the method of how donations are collected is unclear. Is the crowdfunding solely from an online plateform like GoFundMe or were there other collections methods? If there were other collection methods, then which one was most successful? Are successful campaigns funded primarily by online methods, in person methods, or a mix of the two methods? Why are campaigns with zero backers be included in this dateset?

### Digging Deeper 
Louise's biggest concern is likely her funding goal. Would it be possible to reduce her funding goal to increase her chances of success? The data suggests- yes! Although cutting her budget from 10,000 to 5,000 could increase the likehood of her successful form 50% to 70%, that is a substancial cut which could negatively impact the quality of the her play. What would her chances of success be if her goal was 9,000 or 8,000? I would want to narrow the Octcomes vs Goals graph to funding goals of 0 to 11,000 and break down the percentage of success by increments of 500. This would help me make bettter suggestion than cutting her goal from 10,000 to 5,000. 

Another factor I am interested in is the amount of an average donation. Once Louise sets a funding goal, it would be helpful to know how much she should ask backers for. Should she put her time and energy into finding many backers to make smaller donation or a few backers into making larger donations? A line graph comparing successful/failed campagins by numnber of backers and average donation could help Louise maker better decisions about who she will ask to fund her play.  
