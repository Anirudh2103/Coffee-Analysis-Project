# Coffee Analysis Project

Welcome to the Coffee Analysis Project! This project is dedicated to delving into diverse aspects of coffee preferences, trends, and sales within a company.

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Data Sources](#data-sources)
- [Understanding the Data](#understanding-the-data)
- [Combining Data](#combining-data)
- [Visualization](#visualization)

## Introduction

In a world where coffee holds global appeal, understanding the trends and preferences surrounding this beloved beverage is paramount for focused growth and increased revenue. This project demonstrates the application of Excel's advanced functions, including XLOOKUP and INDEX, to extract insights from various data sheets. You will also learn how to consolidate data and create an informative dashboard that presents essential information in a visual format.

## Prerequisites

- Basic understanding of Excel functions.
- Familiarity with pivot tables and charts.

## Data Sources

The dataset used in this project is sourced from [this GitHub repository](https://github.com/mochen862/excel-project-coffee-sales).

## Understanding the Data

- The project revolves around three distinct Excel sheets: Orders, Customers, and Products.
- By identifying unique key values, such as customer IDs or product IDs, data from these sheets will be combined into a unified source.
- The process begins with the aggregation of data from Customers and Products sheets onto the Orders sheet.
- Notably, the customer ID serves as a unique identifier for both Orders and Customers. The XLOOKUP function is employed to extract customer names, emails, and countries from the Customers sheet and populate the Orders sheet:
  - `=XLOOKUP(orders!C2,customers!$A:$A,customers!$B:$B,,0)`
  - `=IF(XLOOKUP(C2,customers!$A:$A,customers!$C:$C,,0)=0,"", XLOOKUP(C2,customers!$A:$A,customers!$C:$C,,0))`
  - `=XLOOKUP(C2,customers!$A$1:$A$1001,customers!$G$1:$G$1001,,0)`
- To handle blank spaces, an IF function accompanies XLOOKUP (as demonstrated with email extraction).
- The same principles can be applied to Coffee Type, Roast Type, and Size using either XLOOKUP or INDEX. Here, the INDEX function is chosen for all three fields:
  - `=INDEX(products!$A$1:$G$49, MATCH(orders!$D2,products!$A$1:$A$49,0),MATCH(orders!I$1,products!$A$1:$G$1,0))`

Stay tuned for a comprehensive exploration of coffee data through analysis and visualization.

For any inquiries, please contact [your.email@example.com](mailto:your.email@example.com).
