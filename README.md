# data-quality-rules-engine

This diagram represents a real-world data quality rules framework I developed.

## Workflow Overview

1. Business users enter plain-language rules in `rules.xlsx`
2. Excel sheet converts these into parameterized SQL snippets
3. These are then ingested into Snowflake in the `DATA_QUALITY` table
4. `dq_builder.py` reads the table and composes a full test query
5. This query becomes part of stored procedure testing or dashboard checks

## Included

- `DQ_process.png`: Visual overview  
- `rules.xlsx`: Template for rule input  
- `generated_sql.sql`: Example SQL built from rules  
- `dq_builder.py`: Python script that compiles and executes the testing logic  

## Tech Highlights

- Collaboration with business via Excel → SQL process  
- Use of Snowflake, Python, stored procedures  
- Automated, scalable data quality checks

## Tools Used

- **Excel** for rule capture and transformation logic  
- **Snowflake** for rule storage and validation execution  
- **Python** for dynamic query generation and QA integration  
- **Stored Procedures** to support repeatable, automated QA checks  

## Why It Matters

This approach empowered business users to define their own rules while ensuring technical enforcement was consistent and scalable. It made our data quality processes transparent, testable, and fast to iterate.

![Data Quality Process Pipeline](DQ_process.png)
