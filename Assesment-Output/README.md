Please read below points for Data Processig/KPI/Deployment/Triggering/Visualization 

**Data Processing:**


1.The dataset is in csv format thus data would be in string datatype by default, Have cleaned and casted columns that are mostly date,int and double datatype for further processing

2.There isn't single "Salary" coulumn so introduced new column "Average Salary" by taking average from existing "Salary Range From" and "Salary Range To" columns. this newly derived Salary column would be used in KPI as well

3.Applied below 3 feature engineering techniques
 a.Extract year  from "Posting date" column (Looking at the dataset it resembles that this column plays a vital role)
 b.binning "job category" in to Top 10 ( Binning is kind of transforming certain set of high-cardinality of data  into       categorical "bins")
 c.There is a column named "Minimum Qual Requirements" that has list of degrees,We are splitting the most valued degree       with other using flag (1-bachelor,master | 0-other)

4.Removing unwanted columns- Identified unused or low profile columns and removed from further taking in to process

5.Each cell in notebook display the sample output for easy reference of each dataframes


**KPI:**

1. All the KPI are performed using processed dataframes
   
2.Average salary per agency for last 2 years - this KPI return  blank result because the latest year in the dataset is   2019.

3 Highes paid skills: For this KPI I've considered key words from the column "Preferred skills" and used UDF to extract the same for calculating highest paid skills API


**Deployment:**

Method 1: Batch deployment using Airflow(We need to package the code in one single file with the extension .py and call the same by creating DAG's) this Airflow can be hosted in AWS EC2 

Method 2: Create a SPark job and submit with "spark=submit" command by writing the .py file in AWS S3(this is for AWS) for Azure cloud we can store in ADSL GEN 2 storage service


**Triggering:**

Manual trigger, schedule trigger,File based trigger...these are the types of trigger we can drive for the job to execute.
One can also use ADF (Azure Data Factory) as well to schedule the data pipelines,Cloud to cloud it depends which tool you use for triggering/orchestration

**Visualization:**

We can use python libraries for visualizing the data, However we can also use Tableau or Power BI for building dashboards on busiess insights


