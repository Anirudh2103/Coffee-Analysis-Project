# Coffee Analysis Project

Welcome to the Coffee Analysis Project! This project aims to analyze various aspects of coffee preferences, trends, and sales of a company. 

## Table of Contents

- [Introduction](#introduction)
- [Prerequisite](#Prerequisite)
- [Data Sources](#data-sources)
- [Understanding the data](#Understanding the data)
- 
  

## Introduction

Coffee is a globally consumed beverage, and understanding the trends and preferences helps you to focus and increase the revenue. In this project, you will see how we can pull the information from other excel sheets using XLOOKUP and INDEX fucntions in Excel. You will also see how we can combine all the data and create a dashboard which shows all the information that we need in a visual format.  

## Prerequisite

- Basic understanding on excel functions.
- Basic understanding on pivot table and charts. 

## Data Sources 
This data is downloaded from https://github.com/mochen862/excel-project-coffee-sales

## Understanding the data

- We have 3 excel sheets Orders, Customers and Products. We want to create a sheet which will combine all the required data from all 3 sheets.
- We need to pull the required data from Customers and Products page to Orders page.
- Step 1: If you look at the orders and customers tab, you will notice customer ID is a unique value. The XLOOKUP function is used to pull customer name, email and country from customers sheet to orders sheet.
  =XLOOKUP(orders!C2,customers!$A:$A,customers!$B:$B,,0)
  =IF(XLOOKUP(C2,customers!$A:$A,customers!$C:$C,,0)=0,"", XLOOKUP(C2,customers!$A:$A,customers!$C:$C,,0))
  =XLOOKUP(C2,customers!$A$1:$A$1001,customers!$G$1:$G$1001,,0)
- If you want to display the blank spaces with any words, you need to use IF function with XLOOKUP function
- Step 2:  


















































