## Seed code - Boilerplate for step 1 - DataMunger Assignment(PLEASE CHANGE THIS README POST CLONNING - SAVE THE INSTRUCTIONS SEPERATELY)

### Problem Statement

As an initial step of building a Utility to get meaningful information out of our Raw data - `as a first step you should be able to parse (decipher) our question. 
In our computing terms, we call this a query.`Our system should be able to interpret this and break it into several parts - so that necessary actions can be triggered to fetch the required information in the proper format.

### STEP 1 - Deciphering the parts of the String (Query)

Please note that the End User interacting with this utility will give out English like instructions and would expect the system to respond with necessary information. The system perceives this a
String of characters and we should be manipulate and break this string into appropriate Data Structures. For Instance,

<Q1> 
<SAMPLE DATA - TABLE> 

<Q2> 
<SAMPLE DATA - TABLE>

-----------
EXPLANATION OF PARTS OF A QUERY HERE

-----------

## Our STEP 1 involves two tasks, given below:

a. Write a program to read the query string as input from the user and split them into words and print the output on console as given below:

    Input String : 	select * from Employee.csv  where  department  = ‘HR’ and salary>=3000

    Output String: 	select
    			    * 
    			    from 
    			    Employee.csv  
    			    where  
    			    department  
    			    = 
    			    'HR'
    			    and 
    			    salary
    			    >=
    			    3000

b. Further enhance your program to now extract certain parts of the same query:

	i.  Get only base part(before `where` word) of the query from the given query string. 

		Input String : select * from Employee.csv where  department  = ‘HR’ and salary>=3000
		Output String : select * from Employee.csv

	ii. Get only filter part(after `where` word) of the query from the given query string. 
	
		Input String : select * from Employee.csv  where  department  = ‘HR’ and salary>=3000
		Output String : department  = ‘HR’ and salary>=3000

	iii. As there will be multiple conditions, seperate each condition and display in different line.
	    
	    Input String : select * from Employee.csv  where  department  = ‘HR’ and salary>=3000
		Output String : 
	                	Condition 1 : department  = ‘HR’ 
		                Condition 2 : salary>=3000
		                
	iv. Split the condition part into variable (before relational operator) and value (after relational operator) and operator.
	    Note: relationa operators are "<, <=, >, >=, =, !="
	
	    Input String : select * from Employee.csv  where  department  = ‘HR’ and salary>=3000
		Output String : 
	                	Condition 1 : 
	                	    variable : department
	                	    operator : = 
	                	    value    : ‘HR’ 
		                Condition 2 : 
	                        variable : salary
	                        operator : >=
	                        value    : 3000
	                        
	v. Extract the logical operators in sequence from the given query string. 
	    Note: Logical operators are "and, or, not"
	    
	    Input String : select * from Employee.csv  where  department = ‘HR’ or department = 'Dev' and salary>=3000
		Output String : 
		        operator 1: or
		        operator 2: and
		        
	vi. Extract the selected fields/information from the given query.
	
	    Input String : select id, name, salary from Employee.csv  where  department = ‘HR’ or department = 'Dev' and salary>=3000
		Output String :
            	id
            	name
            	salary
    
    vii. Extract the order by field from the given string.
        Note : user may need the information in sorted order of a particular field.
        
        Input String : select * from Employee.csv  where  order by salary
		Output String : salary
    
    viii. Extract the group by field from the given string.
        Note : user may need the related information grouped together.
        For Example they may require to see the information department wise.
        
        Input String : select * from Employee.csv  where group by department
		Output String : department
	
	ix. User may required the information like who is getting maximum salary or minimum age etc.. these are called aggregate functions (minimum, maximum, count, average, sum)
	
	    Input String : select count(id), min(age), max(salary) from Employee.csv
		Output String : 
		        Aggregate 1
		            Aggregate Name  : count
		            Aggregate Field : id
	            
	            Aggregate 2
		            Aggregate Name  : min
		            Aggregate Field : age
	            
	            Aggregate 3
		            Aggregate Name  : max
		            Aggregate Field : salary
	
		Note:  Other parts like where clause, order by, group by may be present in the query.

### Expected solution

Displaying various `components/parts` of the query like `selected fields, conditional parts, aggregate fields, groupBy field, OrderBy field` 

### Project structure

The folders and files you see in this repositories, is how it is expected to be in projects, which are submitted for automated evaluation by Hobbes

	Project
	|
	├── resources 			        // If project needs any data file, it can be found here/placed here, if data is huge they can be mounted, no need put it in your repository
	|
	├── com.stackroute.datamunger	    // all your java file will be stored in this package
	|	└── test		                // all your test cases are written using JUnit, these test cases can be run by selecting Run As -> JUnit Test 
	|	└── DataMunger.java	        // This is the main file, all your logic is written in this file only
	|
	├── .classpath			        // This file is generated automatically while creating the project in eclipse
	|
	├── .hobbes   			        // Hobbes specific config options, such as type of evaluation schema, type of tech stack etc., Have saved a default values for convenience
	|
	├── .project			            // This is automatically generated by eclipse, if this file is removed your eclipse will not recognize this as your eclipse project. 
	|
	├── pom.xml 			            // This is a default file generated by maven, if this file is removed your project will not get recognised in hobbes.
	|
	└── PROBLEM.md  		            // This files describes the problem of the assignment/project, you can provide as much as information and clarification you want about the project in this file

> PS: All lint rule files are by default copied during the evaluation process, however if need to be customizing, you should copy from this repo and modify in your project repo


#### To use this as a boilerplate for your new project, you can follow these steps

1. Clone the base boilerplate in your local

	`git clone https://gitlab-dev.stackroute.in/datamunger-java/step-1-boilerplate.git`

2. Remove its remote or original reference

	`git remote rm origin`

3. Add your new repository reference as remote

	`git remote add origin ssh://git@gitlab-dev.stackroute.in:2222/yourusername/your-new-project-repo.git`

4. Commit and Push the project to git

	`git commit -a -m "Initial commit | or place your comments according to your need"`

	`git push -u origin master`

5. Check on the git repo online, if the files have been pushed


### Important instructions for Participants
> - We expect you to write the assignment on your own by following through the guidelines, learning plan, and the practice exercises
> - The code must not be plagirized, the mentors will randomly pick the submissions and may ask you to explain the solution
> - The code must be properly indented, code structure maintained as per the boilerplate and properly commented
> - Follow through the problem statement and stories shared with you

### Further Instructions on Release

*** Release 0.1.0 ***

- Right click on the Assignment select Run As -> Java Application to run your Assignment.
- Right click on the Assignment select Run As -> JUnit Test to run your Assignment.