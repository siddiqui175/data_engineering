# NYC Jobs Data Engineering Assessment

## Dataset
Source - NYC Jobs Dataset (CSV)

## Data Exploration
Numerical Columns: Salary Range From, Salary Range To
Category Columns: Agency, Job Category, Business Title
Text Columns: Preferred Skills, Minimum Qual Requirements
Date Columns: Posting Date

## Data Cleaning & Processing

Cleaning Steps:
Cast salary columns to double
Converted Posting Date to date type

Feature Engineering:
### Average Salary
avg_salary = (salary_from + salary_to) / 2
### Salary Range Difference
salary_range_diff = salary_to - salary_from
### Masters Degree Flag
has_masters_degree (0 or 1)
### Job Posting Age
Calculated difference between current date and posting date.

## KPIs Implemented

1.  Top 10 Job Categories by Number of Postings
2.  Salary Distribution per Job Category
3.  Correlation Between Masters Degree and Salary
4.  Highest Salary Job per Agency
5.  Average Salary per Agency (Last 2 Years)
6.  Highest Paid Skills

## Testing Strategy

Test cases validate:
No null values in avg_salary
Salary range is non-negative
Binary validation of has_masters_degree

## Storage Strategy

Processed dataset stored in Parquet format for efficient analytics

## Deployment Proposal

If deployed:
Deploy Notebook into Azure Databricks
Schedule using Azure Data Factory Pipeline
Store outputs in Data Lake (Parquet format)
Expose Gold tables to BI tools

## Triggering Strategy

The pipeline can be triggered:
On schedule (daily/weekly batch)
On new file arrival (event-based trigger)
Manual trigger for ad-hoc
