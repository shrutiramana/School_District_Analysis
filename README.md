# School_District_Analysis 

## Overview of School District Analysis  - Project for school district analysis for school funding.
###  Purpose 
Maria performed School district analysis but she has been informed that there has been possible evidence that the 9th Graders from Thomas High School might have cheated and their results need to be withheld from the total School District Analysis. She is expected to drop the reading and Math Score for the particular school to NaN and calculate new scores.
She is also expected to do the School District Analysis again and update the following metrics -
* The district summary DataFrame
* The school summary DataFrame 
* The top 5 performing schools, based on the overall passing rate 
* The bottom 5 performing schools, based on the overall passing rate 
* The average math score for each grade level from each school 
* The average reading score for each grade level from each school 
* The scores by school spending per student 
* The scores by school size 
* The scores by school type 


## Resources
- Data Source: schools_complete.csv , students_complete.csv
- Software: conda 4.12.0 , Jupyter Notebooks 

## Results - 

### Deliverable 1  - 

For the challenge we are required  drop “Grade 9th” “Reading & Math Scores” for “Thomas High School”. Below is the snippet of the code that we did 
![drop_9th_grade_score](https://user-images.githubusercontent.com/98556229/168449528-8816be30-f0d6-4101-99f1-80e6a2a34359.png)
This makes the entire values for reading_score & math_score as NaN and can be completely eliminated from our analysis , so that we can scores & summary for the rest of the district.

### Deliverable 2

## District Summary Results
1. For calculating the district summary , we have to eliminate 9th grade students of THS and only consider the (10th-12th grade) students from THS and rest of the schools. Since grade 9 are removed the total count of the students in the district changes and thus affecting the overall summary calculations. 
        * We get the counts of Thomas High School , 9th Graders.  (9th_grade_count.png)
        * We get the total count of students for the district.(
        * Getting the difference of above two to get the net students to consider for the deliverable.(new_student_count.png)
  2. New values of passing_math_percentage,passing_reading & overall_passing_percentage is calculated based on the new student count.
  3. Dataframe is created with new modified values of the columns and data is formatted with appropriate format. Below is the snippet of the new district summary result
  
<img width="1029" alt="New_school_distric_summary" src="https://user-images.githubusercontent.com/98556229/168449552-0afebd5b-e4b1-46b7-906a-52cd00fafb99.png">

## School Summary Results.
In School Summary, all the schools remain same but “% Passing Math , % Passing , % Overall Passing” was recalculated based on the new student count(10th-12th students - excluding9th grade). Then these values are updated in the table to get the new value of per_school_summary_df.


<img width="1112" alt="ne_per_school_summary_df" src="https://user-images.githubusercontent.com/98556229/168449580-c81685b1-d24d-4f79-8626-15853825d06e.png">

## High and low performing schools are found - by sorting the %Overall Passing in descending order .
From the above dataframe we get sort the on %overall ascending and descending order to get the bottom and top 5 schools in the district. Below is the snippet of the code.


<img width="1115" alt="top bottom 5 schools" src="https://user-images.githubusercontent.com/98556229/168449598-5a1f1efd-ce2a-4571-8040-5a5a96948667.png">

## The average math score for each grade level from each school -
The math/reading scores for each grade is found and put in a series and then respective average is calculated for each school , below is the snippet of the code and output.

<img width="435" alt="grade_wise_school_Math_Reading_scores" src="https://user-images.githubusercontent.com/98556229/168449606-5c6e8c26-5f47-4ca9-802b-df5556be7b97.png">


## The scores by school spending per student 
The Schools are divided into bins based on the per capita spending.and we cut the data and put them in respective buckets.

<img width="1151" alt="Scores by School Spending" src="https://user-images.githubusercontent.com/98556229/168449623-b5540976-a791-4c82-a892-4f5b22638d16.png">


## The scores by school size 
Similarly we distribute the data based on the size of school and put them in different buckets below is the snippet for the same.


<img width="1017" alt="school_size bin" src="https://user-images.githubusercontent.com/98556229/168449638-801e7593-f8f7-4545-a65d-b25570d9c694.png">

<img width="937" alt="school_summary_size" src="https://user-images.githubusercontent.com/98556229/168449645-50a90cf4-b426-4c01-b4f7-dbbc340cb898.png">


## The scores by school type 
This can be found by grouping  the data based on the school type and below is the data for the same

<img width="909" alt="school_type" src="https://user-images.githubusercontent.com/98556229/168449664-dcc4848b-b521-451e-92ad-0a57817585c2.png">

## Results 
* How is the district summary affected?
We did district analysis for all schools in the module and same we did for challenge but we dropped all the Reading and Math scores for 9th Grade in Thomas High School. When we did this there is a slight overall difference in results between them. Below are the results for both.


<img width="668" alt="District summary" src="https://user-images.githubusercontent.com/98556229/168449682-e1593de1-4cb6-4910-8c2c-5b29f510b0d0.png">

* How is the school summary affected?
Overall school Summary for others school remain unchanged. For Thomas High School the values had a slight variation for of 10th place of decimal point for all the % Passing Math , %Passing Reading and %Overall had a slight drop in the value, compared to the analysis in module. Below is the snippet.

<img width="829" alt="school_summary" src="https://user-images.githubusercontent.com/98556229/168449693-d3a047cb-68a5-4db3-b4ad-ae2c1236d1b4.png">


* How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?
Thomas High School remain to be in the top 5 schools irrespective of replacing the 9th Grade Math and reading scores. There has been not visible change for the overall average of score for the schools and they remain unchanged.
* How does replacing the ninth-grade scores affect the following:
    * Math and reading scores by grade
        * There has been no change in the Math and Reading scores for other schools , except for the Thomas High Schools where 10th -12 th grades remain same as the previous one except for the 9th grade where scores are dropped and replaced by NaN.Below is snippet of math scores grade wise.
			math_score_grade_wise
			
    * Scores by school spending
        * There has been no overall change in the scores after bucketing based on school spending , as the Thomas High School 9th Graders won’t have any affect on the budget of the schools. While the general observation is Overall Passing % for schools for larger budget din’t fare well.
    * Scores by school size
        * There has been a very slight change in this , since the number of students from Thomas High School 9th graders will be removed from the total count, but this so small then we we format the difference is eliminated.
       
<img width="814" alt="summary_by size compare" src="https://user-images.githubusercontent.com/98556229/168449718-798f08a4-267d-41e0-a227-a5cac25dbe41.png">

    * Scores by school type
        * There has been no impact in this.

### Summary
Following are the observation after reading & math scores for the ninth grade at Thomas High School have been replaced to NaNs.

There has been (small) impact on the Overall district summary which is marginal 
		- Average Math score is reduced by 0.1%
		- %Passing math is reduced by 0.2%
		- % Reading is reduced by 0.3%
		-  %Overall Passing is reduced by 0.1% 
During analysis after replacing the 9th Graders of Thomas High School with NaNs we calculate the % Passing Math & Reading , here we considered total students of THS(9th to 12th)
Where as we have to consider only (10th-12th graders) so the total number of students also drops and then the overall calculations is made, which significantly increases the %performance of THS.


<img width="991" alt="THS_before Total" src="https://user-images.githubusercontent.com/98556229/168449750-1b326922-2bd0-4269-9982-92e40aaa9779.png">


<img width="994" alt="THS_after Total" src="https://user-images.githubusercontent.com/98556229/168449746-2fb26890-ca4e-4a41-96da-da1000f40756.png">





