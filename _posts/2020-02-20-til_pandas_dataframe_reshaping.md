---
layout: post
title: "TIL: DataFrame reshaping in Pandas - melt, unstack"
description: "Quick notes on how to reshape DataFrame in Pandas using melt and unstack"
excerpt: "As a data engineer, part of my daily work involves performing data processing and manipulation on raw data into data that is ready for analysis. As my development team primarily uses Python for our data science workflow, we often use Pandas to perform operations and transformations on datasets before analysing the data. While we primarily use Pandas for data cleaning and engineering as part of the data science process, sometimes we also have to perform complex data transformations to obtain actionable insights that business users can leverage on to improve their processes."
tags: til
---
---

## Background

As a data engineer, part of my daily work involves performing data processing and manipulation on raw data into data that is ready for analysis. As my development team primarily uses Python for our data science workflow, we often use Pandas to perform operations and transformations on datasets before analysing the data. While we primarily use Pandas for data cleaning and engineering as part of the data science process, sometimes we also have to perform complex data transformations to obtain actionable insights that business users can leverage on to improve their processes.

For one of my projects, the objective of the project is to identify opportunities for economies of scale and term agreements with vendors in order to optimize the procurement process. There are different buyers within the organization who have built up their own network of vendors over the years to cater to their different business needs, and the organization would like to find out if there are opportunities to consolidate the vendor network and procurement workflow based on the purchase orders made by the buyers over the years.

For the purpose of illustrating the data manipulation concepts, I will be using a simplified DataFrame that represents the aggregated count and total amount for each vendor-buyer group. Details on the full data manipulation from raw data are in [my TIL blog post](https://datadiaries.commons.host/dataframe-manipulation-sequence-groupby-agg-melt-unstack.html).

### Problem Description

From a Pandas DataFrame, reshape the following DataFrame into a format where order Count and Total Amount could be determined for each Vendor and each Vendor-Buyer combination.

:::python

    >> df = pd.DataFrame(data=
        {'Vendor': ['A', 'A', 'B', 'C', 'C', 'D', 'D', 'E', 'E'],      
        'Buyer':['BU1', 'BU2', 'BU2', 'BU1', 'BU2', 'BU1', 'BU2', 'BU1', 'BU2'],
        'Count':[1, 2, 2, 1, 3, 1, 1, 2, 3]}
        'Total Amount ($)':[1, 15, 60, 103, 262, 30, 23, 179, 171]})

    >> df

        Vendor Buyer  Count  Total Amount ($)
    0      A   BU1      1                 1
    1      A   BU2      2                15
    2      B   BU2      2                60
    3      C   BU1      1               103
    4      C   BU2      3               262
    5      D   BU1      1                30
    6      D   BU2      1                23
    7      E   BU1      2               179
    8      E   BU2      3               171

### What I did
 
**DataFrame.melt** "unpivots" a DataFrame into a format where one or more columns are identifier variables (id_vars), while all other columns, considered measured variables (value_vars), are "unpivoted" to the row axis. This leaves two non-identifier columns, 'variable' and 'value', where 'variable' contains the measured variables and 'value' contains the values corresponding to the measured variables.

:::python

    >> df_melt = df.melt(
            id_vars=['Vendor', 'Buyer'],
            value_vars=['Count', 'Total Amount ($)']
            )

    >> df_melt

        Vendor Buyer          variable  value
    0       A   BU1             Count      1
    1       C   BU1             Count      1
    2       D   BU1             Count      1
    3       E   BU1             Count      2
    4       A   BU2             Count      2
    5       B   BU2             Count      2
    6       C   BU2             Count      3
    7       D   BU2             Count      1
    8       E   BU2             Count      3
    9       A   BU1  Total Amount ($)      1
    10      C   BU1  Total Amount ($)    103
    11      D   BU1  Total Amount ($)     30
    12      E   BU1  Total Amount ($)    179
    13      A   BU2  Total Amount ($)     15
    14      B   BU2  Total Amount ($)     60
    15      C   BU2  Total Amount ($)    262
    16      D   BU2  Total Amount ($)     23
    17      E   BU2  Total Amount ($)    171

**DataFrame.unstack** "pivots" a level of the hierarchial index labels to the column axis and returns a reshaped DataFrame with a new level of column labels, whose inner-most level consists of the pivoted index labels. This implies that a DataFrame which does not have indexing on the row axis will be "pivoted" to a Series.

:::python

    >> df_multiindex = df_melt.set_index(
                        ['Vendor', 'Buyer', 'variable']
                        )

    >> df_multiindex

                                    value
    Vendor Buyer variable
    A      BU1   Count                 1
    C      BU1   Count                 1
    D      BU1   Count                 1
    E      BU1   Count                 2
    A      BU2   Count                 2
    B      BU2   Count                 2
    C      BU2   Count                 3
    D      BU2   Count                 1
    E      BU2   Count                 3
    A      BU1   Total Amount ($)      1
    C      BU1   Total Amount ($)    103
    D      BU1   Total Amount ($)     30
    E      BU1   Total Amount ($)    179
    A      BU2   Total Amount ($)     15
    B      BU2   Total Amount ($)     60
    C      BU2   Total Amount ($)    262
    D      BU2   Total Amount ($)     23
    E      BU2   Total Amount ($)    171

    >> df_multiindex.unstack(level=-2)

                                 value
    Buyer                      BU1    BU2
    Vendor variable
    A      Count               1.0    2.0
           Total Amount ($)    1.0   15.0
    B      Count               NaN    2.0
           Total Amount ($)    NaN   60.0
    C      Count               1.0    3.0
           Total Amount ($)  103.0  262.0
    D      Count               1.0    1.0
           Total Amount ($)   30.0   23.0
    E      Count               2.0    3.0
           Total Amount ($)  179.0  171.0
    
    >>> df_multiindex.unstack(level=-1)

                     value
    variable     Count Total Amount ($)
    Vendor Buyer
    A      BU1       1                1
           BU2       2               15
    B      BU2       2               60
    C      BU1       1              103
           BU2       3              262
    D      BU1       1               30
           BU2       1               23
    E      BU1       2              179
           BU2       3              171

    >>> df_multiindex.unstack(level=0)

                           value
    Vendor                     A     B      C     D      E
    Buyer variable
    BU1   Count              1.0   NaN    1.0   1.0    2.0
          Total Amount ($)   1.0   NaN  103.0  30.0  179.0
    BU2   Count              2.0   2.0    3.0   1.0    3.0
          Total Amount ($)  15.0  60.0  262.0  23.0  171.0

Since I am interested in calculating the overall Count and Total Amount for each Vendor, I pivot the Buyer level to the column axis and retain the Vendor level in the row axis, and calculate the sum along the column axis.

:::python

    >> df_unstack = df_multiindex.unstack(level=-2)

    >> df_unstack['Total'] = df_unstack.sum(axis=1)

    >>> df_unstack
                             value         Total
    Buyer                      BU1    BU2
    Vendor variable
    A      Count               1.0    2.0    3.0
           Total Amount ($)    1.0   15.0   16.0
    B      Count               NaN    2.0    2.0
           Total Amount ($)    NaN   60.0   60.0
    C      Count               1.0    3.0    4.0
           Total Amount ($)  103.0  262.0  365.0
    D      Count               1.0    1.0    2.0
           Total Amount ($)   30.0   23.0   53.0
    E      Count               2.0    3.0    5.0
           Total Amount ($)  179.0  171.0  350.0

## References

- [MultiIndex / advanced indexing - pandas 1.0.1 documentation](https://pandas.pydata.org/pandas-docs/stable/user_guide/advanced.html)
- [Reshaping and pivot tables - pandas 1.0.1 documentation](https://pandas.pydata.org/pandas-docs/stable/user_guide/reshaping.html)
- [pandas.DataFrame.sort_values - pandas 1.0.1 documentation](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.sort_values.html)
- [pandas.DataFrame.melt - pandas 1.0.1 documentation](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.melt.html)
- [pandas.DataFrame.unstack - pandas 1.0.1 documentation](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.unstack.html)
