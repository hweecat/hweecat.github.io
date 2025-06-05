---
layout: post
title: "Modeling Data Fast, Slow, and Back-In-Time: Change-Aware Dimensional Modeling in the Modern Data Stack"
description: "How to design history-preserving data models and reproducible data transformation workflows in modern data warehouses"
excerpt: "In the era of the modern data stack and read-optimized cloud data warehouses, modeling data with versioning enables data teams to track and reproduce history for fast- and slow-changing data over time.

The question is: How do we implement data versioning when modeling our data in the modern data stack?"
tags: til data-modeling
author: ongchinhwee
---
---

In the era of the modern data stack and read-optimized cloud data warehouses, modeling data with versioning enables data teams to track and reproduce history for fast- and slow-changing data over time.

The question is: How do we implement data versioning when modeling our data in the modern data stack?

In this post, I'll explore how we can design history-preserving data models and reproducible data transformation workflows by adopting "change-aware" dimensional modeling practices in the modern data stack.

## Data Versioning

Data versioning is the concept of capturing state changes while keeping track of successive versions of data over time. With multiple versions of the same data record that is saved in the database or data lake, we are able to trace back on historical changes in the data and retrieve previous states of the data if needed - it's a form of time-travel for data.

## Why Does Data Versioning Matter for Data Teams



## Traditional vs Modern Data Versioning Approaches

Traditional data warehousing approaches are based on the era of write-optimized databases with performance constraints on storage and memory. While normalized data structures are useful in online transaction processing (OLTP) systems where large volumes of transactional data can be written and updated frequently, 

Data from relational databases are extracted, loaded into online analytical processing (OLAP) cubes, and queried through analytics and business intelligence tools by business users.

In the modern data stack, 

### Kimball-style Slowly Changing Dimensions

A popular approach to data versioning is the "slowly changing dimensions" methodology, also known as SCDs. The concept of SCDs is first introduced in Kimball's 


### Data Versioning in Modern Data Stack


## "Compute and storage is cheap" != snapshots for everything




## Reproducibility from Source to Data Mart

## Change-Aware Dimensional Modeling



### Immutable Staging Area for Source Data Snapshots

### History-Preserving Dimensions with Validity Periods

### Use Facts when only the Current State Matters



### Building Historical Intermediate Tables from Dimensions

###

## 