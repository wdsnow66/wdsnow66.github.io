---
layout: post
title: "Lessons Learned"
author: "wdsnow"
categories: journal
tags: [documentation,case study]
image: credo_splash.jpg
---

# CREDO Lessons Learned

This Post describes the National Charter School Study project, implementation, and lessons learned from a decade of research data workflow and database design in CREDO at Stanford, resulting in a seminal paper on K-12 School Choice. I was deeply involved in the database design, front-end and back-end implementation, and analyst support. I became increasingly involved with research data management, data cleaning, backup, data use agreements, and ultimately data sanitizaiton. Stata was our tool of choice and it is a power-tool for data analytics. Please visit the project results here, [As a Matter of Fact: The National Charter School Study III](https://ncss3.stanford.edu/){:target="_blank"} .

## CREDO Data
CREDO acquired student test score data from 28+ States under Data Use Agreements. The process of executing, managing, and tracking performance of these DUAs was arduous and an achievement for the team (I helped mostly at the end-of-life stage). This data was gathered year by year into a longitudinal dataset that could be linked by de-identified student ID. Thus student growth could be evaluated year to year. Data on the 130,000 K-12 schools were also collected annually in a local database that could be easily merged into the data workflow based on a unique school ID. I owned the school data, and this data was curated by cross-checking State and Federal data sources. This became your typical ETL but it primarily using Stata and migrating from a local Access database to a split front-end back-end database with a central SQL Server.
![alt text](https://wdsnow66.github.io/assets/img/credo-data.jpg "CREDO Data")

## Data Flow block diagram
The CREDO team created a well-architected, well documented, and well implemented data workflow. This was extremely important to plan and establish up-front since the team had many Researchers processing the data through the workflow. The Researchers would turn-over as they came and went while pursuing their academic career, so careful adherance to the data organization and practices was essential.
![alt text](https://wdsnow66.github.io/assets/img/credo-workflow.jpg "CREDO Workflow")

## Data organization

## Analytic tools and workflow
Stata was at the center of the analytic workflow.  
![alt text](https://wdsnow66.github.io/assets/img/credo-software.jpg "CREDO Software")

## Server Architecture
![alt text](https://wdsnow66.github.io/assets/img/credo-servers.jpg "CREDO Servers")



## Data Security

## Data Sanitization

## Lessons Learned
![alt text](https://wdsnow66.github.io/assets/img/credo-lessons.jpg "CREDO Lessons Learned")

## Lessons Learned Detail
* Desktop Stata workflow and Microsoft Access database
* Central server 
* Split database: Microsoft Access DB and SQL Server 
* Increasing relationship with Stanford central IT 
* Added other research apps ArcMap (Earth Sciences), Tableau
* Improved SFTP
* Increasing relationship with Stanford Security Office
* Improved backups in collaboration with IT
* Improved disaster resilience
* Second server in NDCCH
* Improved secure data delete EOL procedures (and EOL of old server)
* New server switch-over
* Developmental installs of other potential analytic tools e.g. Python, R

## Outline for your Data Plan


