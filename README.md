# Law-Schools

This project defines a relational database schema for storing and managing data related to law schools, including admissions, bar exam results, employment statistics, grants, student debt, gender distribution, and racial demographics.

Database Structure

The schema consists of the following tables:


| Table Name         | Column Name          | Data Type             | Description                                         |
|--------------------|----------------------|-----------------------|-----------------------------------------------------|
| law_schools        | school_id            | INT, PRIMARY KEY      | Unique identifier for a customer.                    |
|                    | school_name          | VARCHAR(255) NOT NULL | First name of the customer.                         |
|                    | city                 | VARCHAR(255)          | Last name of the customer.                          |
|                    | state                | VARCHAR(255)          | Email address of the customer.                       |
|                    | accreditation        | BOOLEAN NOT NULL      | Phone number of the customer.                        |
|admissions	         |admissions_id	        |CHAR(6), Primary key   | unique identifier for admissions record              |
|                    |school_id	            |INT	Foreign key| links to law_schools table|
|                    |total_applications    |	INT	|Total number of applications received
|                    |total_offers	        |INT	|Total number of offers made|
|                    |total_fy_class	      |INT	Total first-year class size|
|                    |ugpa_75th_percentile  |	DECIMAL(3, 2)	|75th percentile undergraduate GPA|
|                    |ugpa_50th_percentile  |	DECIMAL(3, 2)|	50th percentile undergraduate GPA|
|                    |ugpa_25th_percentile  |	DECIMAL(3, 2)	|25th percentile undergraduate GPA|
|                    |lsat_75th_percentile  |	INT	|75th percentile LSAT score|
|                    |lsat_50th_percentile  |	INT	|50th percentile LSAT score|
|                    |lsat_25th_percentile  |	INT	|25th percentile LSAT score|
|bar_exam            |bar_exam_id           |	CHAR(6)	Primary key| unique identifier for bar exam record|
|                    |school_id              |	INT	Foreign key| links to law_schools table|
|                    |graduates_in_2023      |	INT	|Number of graduates in 2023|
|                    |total_first_time_takers	|INT|	Total number of first-time bar takers|
|                    |grads_no_bar_2023      |	INT|	Graduates who did not take the bar exam in 2023|
|                    |grads_no_bar_percentage  |	DECIMAL(5, 2)|	Percentage of graduates who did not take the bar exam|
|                    |grads_no_info          |	INT	|Graduates with no information on bar exam status|
|                    |grads_no_info_percentage	|DECIMAL(5, 2)|	Percentage of graduates with no information|
|                    |total_first_time_passers  |	INT	|Total number of first-time bar exam passers|
|                    |avg_school_pass_percent  |	DECIMAL(5, 2)	|Average bar exam pass rate for the school|
|employment_data     |	employment_id	      |CHAR(6)	Primary key| unique identifier for employment record|
|                    |school_id	INT	Foreign key, links to law_schools table
|                    |full_time_employed	INT	Number of graduates employed full-time
|                    |under_employed	INT	Number of underemployed graduates
|                    |unknown	INT	Number of graduates with unknown employment status
|                    |biglaw_100	INT	Number of graduates employed in BigLaw firms (top 100)
|                    |public_service	INT	Number of graduates employed in public service
|                    |fed_clerks	INT	Number of graduates employed as federal clerks
|                    |law_school_funded	INT	Number of graduates in law school-funded positions
|grants              |	grants_id	CHAR(6)	Primary key, unique identifier for grants record
|                    |school_id	INT	Foreign key, links to law_schools table
|                    |tuition	DECIMAL(10, 2)	Annual tuition cost
|                    |percent_students_receiving_grants	DECIMAL(5, 2)	Percentage of students receiving grants
| debt               |	debt_id	CHAR(6)	Primary key, unique identifier for debt record
|                    |school_id	INT	Foreign key, links to law_schools table
|                    |institution_type	VARCHAR(100)	Type of institution (e.g., public/private)
|                    |avg_loan_disbursement	DECIMAL(12, 2)	Average loan disbursement amount
|                    |percent_borrowing	DECIMAL(5, 2)	Percentage of students borrowing loans
|gender              |	gender_id	CHAR(6)	Primary key, unique identifier for gender demographics
|                    |school_id	INT	Foreign key, links to law_schools table
|                    |total_fy_class_total	INT	Total first-year class size
|                    |total_fy_class_men	INT	Number of male students in first-year class
|                    |total_fy_class_women	INT	Number of female students in first-year class
|                    |total_fy_class_another_gender_identity	INT DEFAULT 0	Number of students identifying as another gender
|                    |total_fy_class_prefer_not_to_report	INT DEFAULT 0	Number of students who prefer not to report gender
|race_demographics   |	race_demographics_id	CHAR(6)	Primary key, unique identifier for race demographics
|                    |school_id	INT	Foreign key, links to law_schools table
|                    |race_unknown	INT DEFAULT 0	Number of students with unknown race
|                    |white	INT DEFAULT 0	Number of white students
|                    |hispanic	INT DEFAULT 0	Number of Hispanic students
|                    |american_indian	INT DEFAULT 0	Number of American Indian students
|                    |asian	INT DEFAULT 0	Number of Asian students
|                    |african_american	INT DEFAULT 0	Number of African American students
|                    |native_hawaiian_pacific_islander	INT DEFAULT 0	Number of Native Hawaiian or Pacific Islander students
|                    |two_or_more_races	INT DEFAULT 0	Number of students identifying with two or more races


Features

Comprehensive Law School Data: Tracks key metrics for law school admissions, bar exams, employment, tuition, debt, and diversity.

Referential Integrity: All foreign key relationships ensure data consistency.

Flexible and Scalable: Can accommodate new data sources and additional metrics over time.

Data Normalization: Ensures efficient storage and retrieval of law school statistics.

Getting Started

Prerequisites

To set up and use this database schema, you will need:

A relational database management system (PostgreSQL, MySQL, or SQLite)

SQL knowledge to create, insert, update, and query data

Installation

Clone this repository:

git clone https://github.com/yourusername/law-school-database.git

Navigate to the project folder:

cd law-school-database

Create the database schema by running:

psql -U your_user -d your_database -f schema.sql

Usage

Use SQL queries to insert, update, or retrieve data.

Generate reports on admissions, bar passage rates, and employment trends.

Analyze tuition and debt burdens across different law schools.

Contributions

Contributions are welcome! Feel free to fork the repository and submit pull requests.

License

This project is licensed under the MIT License.

Contact

For questions or collaboration opportunities, please reach out to Your Name.



