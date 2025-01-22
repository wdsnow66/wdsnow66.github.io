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
CREDO acquired student test score data from 28+ States under Data Use Agreements. The process of executing, managing, and tracking performance of these DUAs was arduous and an achievement for the team (I helped mostly at the end-of-life stage). This data was gathered year-by-year into a longitudinal dataset that could be linked by de-identified student ID. Thus student growth could be evaluated year to year. Data on the 130,000 K-12 schools were also collected annually in a local database that could be easily merged into the data workflow based on a unique school ID. I owned the school data, and this data was curated by cross-checking State and Federal data sources. This became a typical ETL but it was implemented primarily using Stata and migrating from a local Microsoft Access database to a split front-end back-end database with a central SQL Server.

![alt text](https://wdsnow66.github.io/assets/img/credo-data.jpg "CREDO Data")


## Data Flow block diagram
The CREDO team created a well-architected, well documented, and well implemented data workflow. This was extremely important to plan and establish up-front since the team had many Researchers processing the data through the workflow. The Researchers would turn-over as they came and went while pursuing their academic career, so careful adherance to the data organization and practices was essential.

![alt text](https://wdsnow66.github.io/assets/img/credo-workflow.jpg "CREDO Workflow")


## Data organization
The team used a folder format similar to the TIER protocol shown here. This folder structure and readme formed the core for developer collaboration for data processing and analysis steps. File names were extremely precise, processes well documented, and code was peer reviewed.

Thanks to John Borghi of Lane Library and his excellent [Research Data Presentation](https://docs.google.com/presentation/d/1QTVpYNQUxyaEfcf0BZKLjN6pmCviWBA6/edit#slide=id.p39){:target="_blank"} .
![alt text](https://wdsnow66.github.io/assets/img/tier.png "TIER Folders")


## Analytic tools and workflow
The student data, school data, and the analytic tools were all contained within a high-performance Dell server hosted on-premise for security. Stata was at the center of the analytic workflow and the student data was stored in flat files. The School data was stored in an SQL Server database and could be pulled and merged into Stata workflows using the 
Microsoft Open Database Connectivity (ODBC) connectors. Various front-end user interface tools were built for tasks such as data cleaning by interns, data spot-checking by analysts, geocoding, adding metadata, and ad hoc queries.
 
![alt text](https://wdsnow66.github.io/assets/img/credo-software.jpg "CREDO Software")


## Server Architecture
The Server architecture evolved over time from local desktop implementation to a central on-premise high-performane server optimized for Stata mulit-core performance.  We received student data from States using Secure File Transfer Protocol (SFTP) and this function was moved to an independent virtual server to isolate the analytic server from the internet. We added another low-cost virtual server for database work by interns. Another virtual server was built up as an engineering development server with software and folder structure to match the production server, and school data mirrored daily. The engineering dev server could also act as a business continuity mitigation in case the production server was destroyed in a disaster such as fire or earthquake. The production server was securely backed-up to another Dell server configured for large storage and locaded in a different on-premis location. 

![alt text](https://wdsnow66.github.io/assets/img/credo-servers.jpg "CREDO Servers")



## Data Security
Although the data was de-identified and considered medium-security data by Stanford, the group maintained high-level security protocols because of the possible reputation risk to Stanford. All systems were only accessible by identified user IDs via VPN and with two-step authentication. Users were grouped by security level using Stanford's workgroup management system.  

## Data Sanitization
The student data was shared by States under respective Data Use Agreements negotiated by CREDO and vetted by the Stanford Office of Sponsored Research. These agreements generally were time-limited and required destruction of data at end of use. At the conclusion of the study, the data was purged using [NIST SP 800-88 Guidelines for Data Sanitization](https://csrc.nist.gov/pubs/sp/800/88/r1/final).

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

TBD
