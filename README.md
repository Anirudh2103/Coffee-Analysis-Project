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

In a world where coffee holds global appeal, understanding the trends and preferences will help a coffee business to focus in the right areas and increase the revenue. This project demonstrates the application of Excel's advanced functions, including XLOOKUP and INDEX, to extract insights from various data sheets. You will also learn how to consolidate data and create an informative dashboard that presents essential information in a visual format. 

## Prerequisites

- Basic understanding of Excel functions.
- Familiarity with pivot tables and charts.

## Data Sources

The dataset used in this project is sourced from [this GitHub repository](https://github.com/mochen862/excel-project-coffee-sales).

## Understanding the Data

- The complete dashboard is based on 3 sheets: Orders, Customers, and Products.
- By identifying unique key values, such as customer IDs or product IDs, data from these sheets will be combined into a unified source.

## Combining the Data

  - The process begins by combining data from Customers and Products sheets onto the Orders sheet.
  - Notably, the customer ID serves as a unique identifier for both Orders and Customers. The XLOOKUP function is employed to extract customer names, emails, and countries from the Customers sheet and populate the Orders 
     sheet:
  - `=XLOOKUP(orders!C2,customers!$A:$A,customers!$B:$B,,0)`
  - `=IF(XLOOKUP(C2,customers!$A:$A,customers!$C:$C,,0)=0,"", XLOOKUP(C2,customers!$A:$A,customers!$C:$C,,0))`
  - `=XLOOKUP(C2,customers!$A$1:$A$1001,customers!$G$1:$G$1001,,0)`
  - To handle blank spaces, an IF function can be used with XLOOKUP 
  - The same XLOOLUP can be applied to Coffee Type, Roast Type, and Size using either XLOOKUP or INDEX. Here, the INDEX function is used instead of XLOOKUP. Both the INDEX function and the XLOOKUP function are powerful 
    tools in Excel that serve different purposes. Each has its own advantages. 
  - `=INDEX(products!$A$1:$G$49, MATCH(orders!$D2,products!$A$1:$A$49,0),MATCH(orders!I$1,products!$A$1:$G$1,0))`
  - Added Column M to get the Sales. Sales is multiplying unit price (L1) * (E1)
  - To better understand, I changed the Coffee Type and Roast Type to full names intead of using the exisiting shortnames.
  - The names are updated using simple IF function.
    =IF(I2="Rob","Robusta",IF(I2="Exc","Excelsa",IF(I2="Ara","Arabica",IF(I2="Lib","Liberica"))))

## Creating Pivot Charts using the combined data

 - Created a pivot chart which displays "Total Sales based on coffee type". 
   
  ![image](https://github.com/Anirudh2103/Coffee-Analysis-Project/assets/142172393/53a1fbb8-93e9-4d0e-a919-5330085d21bc)

 - I also added 2 splicers, splicers are a visual and interactive feature in Excel that provide a user-friendly way to filter data in PivotTables and PivotCharts.
   
   ![image](https://github.com/Anirudh2103/Coffee-Analysis-Project/assets/142172393/dd57ab53-e5c9-49c8-83a0-d4edbaadc88b)

   ![image](https://github.com/Anirudh2103/Coffee-Analysis-Project/assets/142172393/4439df09-390f-4d0c-96e0-85fcded3a594)

 - Created a pivot chart which displays the sales by Country.

   ![image](https://github.com/Anirudh2103/Coffee-Analysis-Project/assets/142172393/3ce378de-df47-4136-bc5b-d6aa3e523996)


 - Created a pivot chart which shows Top 5 customers based on Sales.
   
   ![image](https://github.com/Anirudh2103/Coffee-Analysis-Project/assets/142172393/3ab0b9b7-cd14-478d-b5fa-b9f61d5162b4)

## Final Dashboard

- Once all the charts are ready, created a new sheet and moved all those charts to this sheet and re-arranged as follows: 

  ![image](https://github.com/Anirudh2103/Coffee-Analysis-Project/assets/142172393/b72017d7-5fe8-4508-971f-58d5b54bf49a)



