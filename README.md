# PWC Power BI Virtual work experience- Call Centre Trends
![PwC Power BI Virtual Case Experience (1)](https://user-images.githubusercontent.com/118357991/227764081-750f7560-c9f7-4563-9cb3-74186769cb42.png)

## Table of Contents :

- [Problem Statement](https://github.com/yogeshkasar778/PWC_task-Call_Centre_trends-dashboard/edit/main/README.md#problem-statement-)
- [Datasource](https://github.com/yogeshkasar778/PWC_task-Call_Centre_trends-dashboard/edit/main/README.md#datasource-)
- [Data Preparation](https://github.com/yogeshkasar778/PWC_task-Call_Centre_trends-dashboard/edit/main/README.md#data-preparation)
- [Data Modelling](https://github.com/yogeshkasar778/PWC_task-Call_Centre_trends-dashboard/edit/main/README.md#data-modeling)
- [Data Analysis (DAX)](https://github.com/yogeshkasar778/PWC_task-Call_Centre_trends-dashboard/edit/main/README.md#data-analysis-dax)
- [Data Visualization Dashboard](https://github.com/yogeshkasar778/PWC_task-Call_Centre_trends-dashboard/edit/main/README.md#data-visualization-dashboard-)
- [Insights](https://github.com/yogeshkasar778/PWC_task-Call_Centre_trends-dashboard/edit/main/README.md#insights-)


## Problem Statement :
In this project Create a dashboard in Power BI for the call center manager that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset.

Possible KPIs include (but not limited to):

- Overall customer satisfaction
- Overall calls answered/abandoned
- Calls by time
- Average speed of answer
- Agent’s performance quadrant -> average handle time (talk duration) vs calls answered

## Datasource :

Dataset used for this task was presented by [Pwc](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html) and call centre trends dataset:

Dataset: [Call Centre Trends](https://github.com/yogeshkasar778/PWC_task-Call_Centre_trends-dashboard/blob/main/01%20Call-Center-Dataset.xlsx)

## Data Preparation:

Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

Call Centre Trends dataset is give table named:

- `Call Center trends dataset` which has `10 columns and 5000 rows` of observation

Data Cleaning for the dataset was done in the power query editor as follows:

- Removed Unnecessary columns
- Removed Unnecessary rows
- Each of the columns in the table were validated to have the correct data type

## Data Modeling:

And then dataset was cleaned and transformed, it was ready to the data modeled.

- The `measure table` and `call centre trends` tables as show below:

-![Screenshot (37)](https://user-images.githubusercontent.com/118357991/227766088-7fe8f2b3-b4b3-4cfd-a925-0895874ea956.png)

## Data Analysis (DAX):

Measures used in  all visualization are:

- Average of seed of answerd = `AVERAGE('call centre trends'[Speed of answer in seconds])`

- Average of statisfaction = `AVERAGE('call centre trends'[Satisfaction rating])`

- Count satisfation rating = `COUNT('call centre trends'[Satisfaction rating])`

- Overall Customer Satisfation = `DIVIDE([Possitive satisfation rating],[Count satisfation rating],0)`

- Possitive satisfation rating = `CALCULATE(COUNT('call centre trends'[Satisfaction rating]),FILTER('call centre trends','call centre trends'[Satisfaction rating] IN {4,5}))`

- resolved calls = `COUNTX(FILTER('call centre trends','call centre trends'[Resolved] = "Yes"), 'call centre trends'[Resolved])`

- Unresolved calls = `COUNTX(FILTER('call centre trends','call centre trends'[Resolved] = "No"), 'call centre trends'[Resolved])`

- total calls =  `CALCULATE('Table'[total calls answered] + 'Table'[total calls unanswred])`

- total calls answered = `COUNTX(FILTER('call centre trends','call centre trends'[Answered (Y/N)] = "Yes"),'call centre trends'[Answered (Y/N)])`

- total calls unanswred =`COUNTX(FILTER('call centre trends','call centre trends'[Answered (Y/N)] = "No"), 'call centre trends'[Answered (Y/N)])`

## Data Visualization (Dashboard) :

Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

Dashboard: [View Dashboard](https://www.novypro.com/project/yogeshkasar97)

Shows visualizations from Call Center Trends :

| Call Centre Trends (Overview) |
| ----------- |
| ![PWC Task 1 - Call Centre Dashboard-1](https://user-images.githubusercontent.com/118357991/227767359-463d93ee-5436-4f6a-ab7d-705c11d0dfbf.png) |


| Call Centre Trends (Agent's Performance) |
| ----------- |
| ![PWC Task 1 - Call Centre Dashboard-2](https://user-images.githubusercontent.com/118357991/227767508-8667b273-6a78-40fa-bc20-78fc88c155cc.png) |

## Insights :

As shown by Data Visualization, It can be deduced that:

- Most of the satisfaction ratings from each call are 3 and 4.
- The average satisfaction rating has decreased over the span of three months. January brought the highest satisfaction rating and march the lowest.
- The percentage of issue resolved in January was the highest, with a dip in February. It increased again in march.
- The majority of calls come in the morning.
- The average speed of answer by Joe is the highest.
- The call resolution rate of Jim is the highest, even though the average speed of his answers is lower compared to those of Joe, Martha and Dan. The call answered by - him are also higher than the average number of calls answered.
- Becky's speed of answer is the lowest among all, and her rate of calls resolved is higher. She is in the 5th position in the call resolution rate. 
- Martha has the highest  speed of answered in the sec

---




