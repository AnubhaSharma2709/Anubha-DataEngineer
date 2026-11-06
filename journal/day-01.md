# Day 01 — Starting My Data Engineering Journey

*6 November 2026*

Today marks the beginning of my structured learning journey. I am focusing on three areas simultaneously:

1. Data Engineering — Learning from Krish Naik.
2. Python DSA — Practising problems on LeetCode and GeeksforGeeks.
3. Google Cloud — Starting the Google Cloud Skills Partner programme and hands-on skill badge learning.

---

# 1. DATA ENGINEERING — Understanding Big Data

*Learning source: Krish Naik's Data Engineering course*

## Q1. What is an RDBMS?

RDBMS stands for Relational Database Management System.

It stores data in structured tables consisting of rows and columns. SQL is used to interact with relational databases.

RDBMS works well for structured data and many transactional applications.

However, as data grows in volume and complexity, traditional database architectures may face challenges with storage, processing and scalability.

## Q2. Why do we need Big Data technologies?

As applications grow, the amount of data generated also increases.

Some challenges with handling large datasets include:

1. Scalability: There are physical limits to increasing the resources of a single machine.
2. Data growth: Large datasets may require partitioning and distributed storage.
3. Processing: Large-scale operations can become slow or resource-intensive.
4. Unstructured data: Images, videos and other complex formats may not fit naturally into relational tables.

This is where Big Data technologies become useful.

## Q3. What is Big Data?

Big Data refers to datasets that are too large, complex or fast-moving to be efficiently handled using traditional data-processing systems.

Some common sources of Big Data include:

- Growth of the internet.
- Social media platforms.
- IoT devices and sensors.
- E-commerce platforms such as Amazon.
- Online transactions and customer interactions.

For example, Amazon generates data through product searches, purchases, reviews and customer interactions.

This data can be collected and analysed to understand customer behaviour and improve business decisions.

## Q4. What are the 5 Vs of Big Data?

The 5 Vs describe the major characteristics and challenges associated with Big Data.

| Characteristic | Meaning | Example |
|---|---|---|
| Volume | Amount of data generated | Billions of transactions |
| Velocity | Speed at which data is generated and processed | Live banking transactions |
| Variety | Different formats of data | Tables, JSON, images and videos |
| Veracity | Quality and accuracy of data | Missing or duplicate records |
| Value | Useful insights extracted from data | Understanding customer behaviour |

### Understanding Velocity in more detail

Data can be processed in three common ways:

**1. Real-time processing**

Data is processed immediately or with very low latency.

Example: A bank checking whether a credit card transaction is suspicious.

**2. Near-real-time processing**

Data is continuously generated but processed with a small delay.

Example: A dashboard that refreshes every 2–5 minutes.

**3. Batch processing**

Data is collected and processed at scheduled intervals.

Example: Generating a credit card statement at the end of the billing cycle.

### Understanding Variety

Data can be classified into three categories:

- Structured data: Organised in predefined tables and columns.
- Semi-structured data: Has some organisational structure but does not follow a rigid relational schema. Example: JSON and XML.
- Unstructured data: Does not follow a predefined tabular structure. Example: Images, videos and audio.

## Q5. What is a distributed system?

As the size and complexity of data increase, one machine may not have sufficient resources to process everything efficiently.

A distributed system uses multiple independent machines that communicate and work together.

Each machine is called a **node**.

A group of connected machines working together is called a **cluster**.

Instead of processing a large dataset on one machine, the workload can be distributed across multiple machines.

## Q6. What is the difference between vertical and horizontal scaling?

**Vertical scaling:**

Increasing the resources of an existing machine, such as CPU, RAM or storage.

**Horizontal scaling:**

Adding more machines to distribute the workload.

Example:

- Vertical: Increasing one machine's capacity from 8 GB RAM to 16 GB RAM.
- Horizontal: Adding more machines to a cluster.

Horizontal scaling is particularly important in distributed Big Data architectures.

## Q7. What resources are required to process large datasets?

Three important resources are:

1. Storage — HDD and SSD.
2. Memory — RAM.
3. Processing power — CPU cores.

As data size and complexity increase, the system may require more of these resources.

## Q8. What makes a good Big Data system?

A good Big Data system should have four important characteristics.

**1. Scalability**

It should handle increasing data volumes and processing requirements.

This includes:

- Storage scalability.
- Processing or computational scalability.

**2. Reliability and Fault Tolerance**

The system should continue operating or recover when an individual component fails.

For example, if one machine in a cluster fails, the system should be able to recover or continue using other available resources.

**3. Cost Effectiveness**

The system should balance performance and scalability with infrastructure costs.

**4. Security and Data Privacy**

Data should be protected from unauthorized access.

## Q9. What is the difference between on-premises and cloud infrastructure?

| On-premises | Cloud |
|---|---|
| Infrastructure is owned or managed by the organisation. | Infrastructure is provided by a cloud provider. |
| Requires significant initial investment. | Often follows a pay-as-you-go model. |
| Hardware maintenance is the organisation's responsibility. | Underlying infrastructure is largely managed by the provider. |
| Scaling may require purchasing hardware. | Resources can be provisioned more flexibly. |

Examples of cloud providers include AWS, Microsoft Azure and Google Cloud Platform.

## Q10. What are the different types of cloud deployment models?

**1. Public Cloud**

Infrastructure provided by a cloud provider and used by multiple customers.

Examples: AWS, Azure and GCP.

**2. Private Cloud**

Cloud infrastructure dedicated to a single organisation.

**3. Hybrid Cloud**

A combination of public and private cloud infrastructure.

**4. Community Cloud**

Infrastructure shared by organisations with common requirements, such as security or compliance needs.

---

# 2. PYTHON DSA — Coding Practice

*Platforms: LeetCode and GeeksforGeeks*

Today's coding practice focused on understanding mathematical logic, loops, conditions and Python operators.

## Problem 1: Prime Number

**Question: Given an integer n, determine whether it is a prime number.**

### What is a prime number?

A prime number is a number greater than 1 that has exactly two factors: 1 and itself.

Examples: 2, 3, 5, 7 and 11.

Numbers such as 0 and 1 are not prime.

### My approach

1. First, check whether the number is less than or equal to 1.
2. If yes, return False.
3. Start checking divisibility from 2.
4. Use the modulo operator to check whether the number is divisible by another number.
5. If a divisor is found, return False.
6. If no divisor is found, return True.

### My basic implementation

```python
class Solution:
    def isPrime(self, n):
        if n <= 1:
            return False

        for i in range(2, n):
            if n % i == 0:
                return False

        return True
```

### Understanding the code

- `n <= 1`: Handles numbers that cannot be prime.
- `range(2, n)`: Checks possible divisors from 2 to n-1.
- `n % i == 0`: Checks whether the remainder is zero.
- `return False`: A divisor has been found.
- `return True`: No divisor was found.

### Can we optimize this?

Yes. We only need to check divisors up to the square root of n.

```python
class Solution:
    def isPrime(self, n):
        if n <= 1:
            return False

        i = 2

        while i * i <= n:
            if n % i == 0:
                return False
            i += 1

        return True
```

**Complexity:**

- Basic approach: O(n) time.
- Optimized approach: O(√n) time.
- Space: O(1).

The important learning is that we do not need to check every number to determine whether a number is prime.

## Problem 2: Add Digits

**Question: Given an integer, repeatedly add its digits until the result contains only one digit.**

Example:

Input: `38`

First iteration: 3 + 8 = 11

Second iteration: 1 + 1 = 2

Output: `2`

### Which Python concepts are required?

- While loops.
- Modulo operator `%`.
- Integer division `//`.
- Variable reassignment.

### How do we extract individual digits?

We use two operators:

```python
digit = num % 10
num = num // 10
```

For example, if `num = 123`:

- `123 % 10` gives 3.
- `123 // 10` gives 12.

The modulo operator extracts the last digit, while integer division removes it.

### My logical approach

I used two while loops.

1. The inner loop extracts individual digits and calculates their sum.
2. The outer loop repeats the process until only one digit remains.

### Code

```python
class Solution:
    def addDigits(self, num: int) -> int:

        while num >= 10:
            total = 0

            while num > 0:
                digit = num % 10
                total = total + digit
                num = num // 10

            num = total

        return num
```

### Dry run: num = 1234

| Step | Operation | Result |
|---|---|---|
| 1 | 1234 % 10 | 4 |
| 2 | 1234 // 10 | 123 |
| 3 | 123 % 10 | 3 |
| 4 | 123 // 10 | 12 |
| 5 | 12 % 10 | 2 |
| 6 | 12 // 10 | 1 |
| 7 | 1 % 10 | 1 |

First sum: 4 + 3 + 2 + 1 = 10.

The outer loop runs again.

1 + 0 = 1.

Final output: `1`.

### Important learning

The inner loop extracts and adds individual digits.

The outer loop repeats the digit-summing operation until the number becomes a single digit.

---

# 3. GOOGLE CLOUD — Hands-on Learning

*Learning source: Google Cloud Skills Boost / Skills Partner Programme*

Today I started my Google Cloud learning journey through the Skills Partner programme.

I also worked on the hands-on lab:

**GSP430 — Creating a Data Transformation Pipeline with Cloud Dataprep**

The lab involved preparing an e-commerce dataset using BigQuery, Cloud Dataprep and Dataflow.

## Q1. What is data transformation?

Data transformation is the process of converting raw data into a clean, consistent and useful format.

Raw datasets may contain:

- Missing values.
- Duplicate records.
- Incorrect data types.
- Unnecessary columns.
- Inconsistent values.

Data needs to be prepared before it can be reliably used for reporting and analysis.

## Q2. What is BigQuery?

BigQuery is Google Cloud's fully managed, serverless data warehouse.

It allows us to store and analyse large datasets using SQL.

In this lab, BigQuery was used as both the source and destination of the transformation pipeline.

## Q3. What is Cloud Dataprep?

Cloud Dataprep, used in this lab through Alteryx Designer Cloud, is a visual data exploration and preparation tool.

It allows us to:

- Explore datasets.
- Identify missing values.
- Change data types.
- Remove duplicate records.
- Filter unwanted records.
- Create calculated columns.

It provides a visual interface for preparing data instead of manually writing every transformation.

## Q4. What is Dataflow?

Dataflow is Google Cloud's managed service for executing data-processing pipelines.

In this lab, Dataflow was selected as the execution environment for the transformation job.

## Q5. How did the data transformation pipeline work?

The overall workflow was:

```text
Raw E-commerce Data
        |
        v
     BigQuery
        |
        v
  Cloud Dataprep
        |
        v
 Data Transformation
        |
        v
 Dataflow + BigQuery
        |
        v
 Final Reporting Table
```

The final output was a BigQuery table named:

`revenue_reporting`

## Q6. What is a BigQuery dataset?

A dataset is a logical container used to organise tables and other resources in BigQuery.

In this lab, I created a dataset named:

`ecommerce`

I also created a table named:

`all_sessions_raw_dataprep`

### SQL used

```sql
CREATE OR REPLACE TABLE
  ecommerce.all_sessions_raw_dataprep

OPTIONS(
  description="Raw data from analyst team to ingest into Cloud Dataprep"
) AS

SELECT *
FROM `data-to-insights.ecommerce.all_sessions_raw`
WHERE date = '20170801';
```

### Understanding the query

- `CREATE OR REPLACE TABLE`: Creates a table or replaces an existing one.
- `SELECT *`: Retrieves all columns.
- `FROM`: Specifies the source table.
- `WHERE`: Filters the records.

The query selected approximately 56,000 records for August 1, 2017, rather than processing the entire source dataset.

## Q7. What is data profiling?

Data profiling means examining a dataset to understand its structure, completeness, distribution and quality.

In the lab, I explored:

- Number of columns: 32.
- Missing values.
- Data types.
- Column distributions.
- Transaction information.
- Countries and acquisition channels.

An important observation was that some columns contained missing values, while others had data type mismatches.

Understanding the data before transforming it is an important step in building a reliable pipeline.

## Q8. Why did I change productSKU from Integer to String?

A product SKU is an identifier, not a mathematical quantity.

It may contain letters, numbers or leading zeros.

For example:

`GGOEGOCD078399`

Therefore, storing it as a String is more appropriate than treating it as an Integer.

## Q9. Why did I remove duplicate records?

Duplicate records can lead to incorrect analytical results.

For example, if the same transaction is counted more than once, revenue calculations may become inflated.

However, duplicates should be identified using the correct business definition of uniqueness.

## Q10. What is a composite key?

A composite key combines multiple columns to identify a record.

In the lab, I combined:

- `fullVisitorId`
- `visitId`

to create:

`unique_session_id`

This was necessary because `visitId` alone was not globally unique.

Conceptually:

```text
unique_session_id = fullVisitorId + "-" + visitId
```

## Q11. Why did I create eCommerceAction_label?

The original `eCommerceAction_type` column contained integer values representing different e-commerce actions.

For example:

| Value | Meaning |
|---|---|
| 0 | Unknown |
| 1 | Product list click |
| 2 | Product detail view |
| 3 | Add to cart |
| 4 | Remove from cart |
| 5 | Checkout |
| 6 | Completed purchase |
| 7 | Refund |
| 8 | Checkout options |

I created a new column called `eCommerceAction_label` to convert these numeric codes into meaningful descriptions.

This makes the data easier to understand and use in reporting.

## Q12. Why did I divide transaction revenue by 1,000,000?

The source dataset stored `totalTransactionRevenue` multiplied by 10⁶.

For example:

```text
2400000 / 1000000 = 2.40
```

I divided the field by 1,000,000 to restore the original revenue value.

I then changed its data type to Decimal because monetary values require appropriate decimal precision.

## Q13. How was the final data published?

After completing the transformations, I configured the Run Job settings.

The selected execution environment was:

`Dataflow + BigQuery`

The output destination was:

- Dataset: `ecommerce`
- Table: `revenue_reporting`

I selected the option to drop and recreate the destination table on each run.

After executing the job, I refreshed BigQuery and verified that the final reporting table existed.

This completed the lab.

---

# 4. WHAT I LEARNED TODAY

### Data Engineering

- Started learning Big Data fundamentals.
- Understood the 5 Vs of Big Data.
- Explored distributed systems, nodes and clusters.
- Learned about vertical and horizontal scaling.
- Understood cloud deployment models.

### Python DSA

- Practised Prime Number.
- Practised Add Digits.
- Understood modulo and integer division.
- Worked with nested while loops.
- Explored a more optimized prime-checking approach.

### Google Cloud

- Started the Google Cloud Skills Partner programme.
- Explored BigQuery.
- Worked with Cloud Dataprep.
- Understood the role of Dataflow.
- Completed the GSP430 data transformation workflow.
- Learned data profiling, cleaning, enrichment and publishing.

### Three things I want to remember

1. Big Data is not only about the amount of data; speed, variety, quality and value matter too.
2. Distributed systems help process large datasets by using multiple machines.
3. Data engineering is not just about moving data. It is also about cleaning, transforming and making data useful.

---

# 5. WHAT I PLAN TO LEARN NEXT

- Continue the Data Engineering course by Krish Naik.
- Practise more Python problems on LeetCode and GeeksforGeeks.
- Complete the next Google Cloud hands-on lab.
- Revise today's Big Data concepts and Python logic.

**Today's reflection:**

I am starting with the fundamentals and building my understanding one concept at a time. I want this journal to become a record of what I actually learn, practise and understand.

*One day. One lesson. One step forward.*
