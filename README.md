# TixPix

# Background and Role

TixPix is a fictional ticket platform that allows users to buy tickets for live sports, concerts, conferences, and theater events.

# Ask
Business Task: Optimize ticket sales and event engagement by analyzing revenue trends, attendee demographics, and check-in rates to improve future event planning and marketing strategies.

**Business Questions:**

1.	Which events generated the highest revenue, and what factors contributed to their success?

2.	What are the key demographics of attendees, and how can marketing be optimized to target high-value customers?

3.	How does the check-in rate vary across events and ticket types, and what strategies can improve attendance?

I am assigned to answer the first question, and thus my analysis will be focused on which events generated the highest revenue and what factors contributed to their success.

**Key Stakeholders:**

•	Ben Hurr — Director of the marketing team and my manager.

•	TixPix executive team

# Prepare

To begin this project, I went to Kaggle.com and downloaded a CSV file that contained ticketing information about fictional customers. The spreadsheet contained name, events, gender, city, and various other information that relates to customers and ticket sales totaling twenty columns. These columns are as follows:

1.	EventID
2.	TicketID
3.	TicketType
4.	TicketPrice
5.	TicketAvailability
6.	TicketSalesStartDate
7.	TicketSalesEndDate
8.	FirstName
9.	LastName
10.	Email
11.	CustomerAge
12.	CustomerGender
13.	City
14.	CheckInStatus
15.	EventName
16.	EventType
17.	EventDate
18.	EventTime
19.	EventOrganizer
20.	EventDuration

# Process
**Tools – Excel and SQLite**

**Data Cleaning and Exploration**

To clean the dataset, I used Excel and SQLite. In Excel I removed various columns that I believed was not needed for this assignment, checked for duplicates, made columns more uniformed and split the name column into “First Name” and “Last Name”. Lastly, I added a “tickets bought” column to show how many tickets each customer bought and used the formula “=RANDBETWEEN” to generate random numbers between 1 and 6.
In SQLite, I added one column to the database and titled it “sales_channel” to show if a ticket purchase was made online, at the box office or by a third-party vendor.
 
![Adding sales channel column](https://github.com/user-attachments/assets/2619d718-cd41-4d89-9d92-601aed353b88)
![Adding sales channel coulmn Pt2](https://github.com/user-attachments/assets/2b57f005-2f71-459b-9e6e-1dfb7a62c969)

# Data Analysis & Visualization

Now that I have cleaned the data and made some additions, I will go back to answering the business question:
Which events generated the highest revenue, and what factors contributed to their success?
With the data, I can extract the information that will help answer this question. Here is how I will approach it using the available data:


**Calculate Total Revenue Per Event**

We can calculate the total revenue per event by using the SUM function in SQLite multiplying ticket price by tickets bought to effectively calculate revenue for each event. 

![Total Rev Per Event](https://github.com/user-attachments/assets/50e904f4-dfec-43a3-8699-54f3761e44ce)

After inputting the query, we find that the top event with the most revenue was “Google IO” generating $13,644,500, “Future Shapers” generating $13,622,500 and “Machine Learning” generating $10,932,000. In contrast, “Green Fiesta” was the lowest performing event, generating $5,498,000, indicating potential gaps in promotion or pricing.

![Event Performance DB](https://github.com/user-attachments/assets/b8749ae0-4a68-4ad1-968e-30763f95446a)

A key insight based off the bar graph above is that conferences and seminars are the two most revenue generating events which indicate the popularity of those events along with excellent marketing and promotion of those events.

**Which Ticket Types Were Most Profitable?**


To determine which ticket types were profitable, I queried in SQLite to calculate the sum and used COUNT to get the total number of tickets sold to each event.

![Analyze Rev by Ticket Type](https://github.com/user-attachments/assets/cbc53eb9-236e-41bf-90db-dd6c09ca0e40)

General admission tickets contributed 49% of total revenue across all events, generating a total of $39,822,500. This indicates that general admission tickets were the most sought after and that the pricing strategies were the most effective. Pre-sale tickets made up 29% of total revenue, which indicates that marketing for the events was effective. 

![Ticket Type Pie Chart](https://github.com/user-attachments/assets/a2d8f28b-24d2-4de0-b26f-de5ab649808d)

VIP tickets only contributed 21%, $17,036,00 of total revenue, which you can see in the pie chart above. There is room for improvement, possibly a slight decrease in pricing, an increase in general admission tickets or a more concentrated effort in promoting VIP tickets.

**What Were the Best Sales Channel?**

The sales channels at TixPix are Box Office, Online and Third-Party Vendor. I queried in SQLite to compare the sales channels to see which sales channel generated the most profit. The results from the query showed that the “Third-Party Vendor” was the primary revenue generator for the events that TixPix offered.

![Compare Sales Channel](https://github.com/user-attachments/assets/e7665237-fe79-49d6-81f7-b5ad64c00297)

Regarding “Third-Party Vendor” sales, resulted in 80% of revenue across six different events, making it the most successful sales channel. 

![Sales Channel Comparison](https://github.com/user-attachments/assets/9dbaf068-81e9-4f4e-99a4-ac1665dff0a9)

However, “Online” sales lagged contributing only 7%. This suggests that marketing efforts should focus on improving online presence and boost on-site purchases.

# Act

After conducting analysis of the data, we have discovered valuable insight into how to improve our sales in various ways. Below, I will suggest recommendations for improving our sales strategies:
1.	Top events should be analyzed to see if the success of those events can be replicated to the lesser events and possibly expand upon the top events. Experimenting with dynamic pricing should help with the less performing events.
2.	Ticket pricing strategies like increasing the price of general admission tickets, slightly decreasing VIP tickets and or adding or expanding premium benefits of VIP tickets.
3.	Sales channels, specifically Box Office and Online need a drastic overhaul of marketing to improve engagement. One idea is to add an incentive like a in-person promotion to increase box office sales.









