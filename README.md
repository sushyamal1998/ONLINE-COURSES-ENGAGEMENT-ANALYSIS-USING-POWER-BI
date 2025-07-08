# ONLINE-COURSES-ENGAGEMENT-ANALYSIS-USING-POWER-BI
Analyzing patteren in online course engagement to understand viewer performance based on course duration, course language etc.

## Overview
This Power BI project analyze **online course dataset** to explore how course duration impact on viewer, subtitle language and to understand the performance in different categories, subcategories.

## Tools Used
- **Power BI:** for data visualization and interactive Dashboard
- **Power query:** for cleaning and transforming data
- **DAX:** for creating calculated measures and advanced insights


## Dataset
- **File name:** Online_Courses.csv
- **Description:** This dataset contain detail on courses of E-learning platform which include column like category,subcategory, viewers, instractor, duration of courses etc.

## Analysis and Dashboard features
### Cleaning dataset
- From dataset first remove duplicate rows, fill missing values, remove extra space etc.
### Create New table
- Create a new table, Instructor which contain column Attribute, category, Customer_id, insructor, instructor_rank(create using DAX), ratting


### Dax Measures
- **Instructor Rank:** To give the rank of each instructor
```dax
 instractor_rank = if(rankx(all(Instructor[Instructors]), calculate(AVERAGE(Instructor[Rating])))<=3,
                  calculate(AVERAGE(Instructor[Rating])),blank())
```
- **category_rank_by_viewer**
```dax
category_rank_by_viewer = if(rankx(all(Online_Courses[Category]),calculate(AVERAGE(Online_Courses[Number of viewers])))<6,
                  calculate(average(Online_Courses[Number of viewers])), blank())
```


### Interactive Dashboard
- **Stacked Column Chart:** Course tupe and Count of course_id, Average number of viewers by Sub-Category
- **Pie Chart:** Course_type and Language
- **line Chart:** Viewers and Language Subtitle
- **Matrix:** Category and category_rank_by_viewer, Instructors and Rank


## Key insights
- Data Science category has most viewer, then information technology, computer Science
- Most of course are english language and they are average 50-60 hours course by viewer preference
- Flexible courses attract more engagement in soft-skill areas


## Conclusion
Through this project, i explored how course duration affects engagement across different categories and sub-categories on an e-learning platform.
- Shorter courses tend to drive higher views, particularly in technical domains
- Shorter courses tend to drive higher views, particularly in technical domain


  
















































impact on viewer
