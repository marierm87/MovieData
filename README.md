# MovieData
A data analysis project examining movie trends from 2012-2016.
# 🎬 Movie Data Analysis Dashboard (2012–2016)



## 📑 Table of Contents

- [📌 Project Overview](#project-overview)

- [📊 Data Sources](#data-sources)

- [🧰 Tools Used](#tools-used)

- [🧹 Data Cleaning Process](#data-cleaning-process)

- [📈 Dashboard & Visualizations](#dashboard--visualizations)

- [🔍 Key Insights](#key-insights)

- [🧮 M Language Example](#m-language-example)



---



## 📌 Project Overview



This project analyzes movie performance data from 2012 to 2016 using Excel and Power Query.  

It identifies trends in budget, revenue, genres, and actor performance. A dashboard was created to visually summarize findings and support recommendations.



---



## 📊 Data Sources



**Dataset:** `Movie Data Homework.xmls`  

📥 [Download the dataset](https://github.com/Irene-arch/Documenting_Example?tab=readme-ov-file)



**Key columns include:**

- Movie Title

- Genre(s)

- Main Actors

- Budget ($)

- Box Office Revenue ($)

- Release Date



---



## 🧰 Tools Used



- **Excel** – Pivot tables, charts, dashboards  

- **Power Query** – Data loading, splitting genres, cleaning nulls  

- **GitHub** – Version control and project presentation  



---



## 🧹 Data Cleaning Process



1. Loaded the `.xmls` file using Power Query  

2. Split multi-genre and multi-actor columns  

3. Removed nulls and errors  

4. Formatted numeric fields (budget, revenue)  

5. Merged and grouped data for analysis  



---



## 📈 Dashboard & Visualizations



The dashboard includes:



- 📌 **Slicers** for Genre, Main Actor, and Release Year  

- 📊 **Top 10 Genres by Box Office Revenue**  

- 🎥 **Top Movies by ROI and Revenue**  

- 💸 **Top 5 Movies by Budget**  

- 👤 **Top 5 Main Actors by Revenue**  

- 📅 **Monthly Revenue Trends**  

- 📉 **Worst Movie by ROI**



📷 _Dashboard preview:_  

_Add a screenshot of your dashboard here if uploading to GitHub._



---



## 🔍 Key Insights

This dashboard is designed to deliver dynamic, user-driven analysis. Instead of displaying fixed results, it allows users to interactively explore how performance metrics like ROI, genre popularity, and actor success change year by year. With slicers for genre, main actor, and release date, the dashboard becomes a powerful tool for discovering trends and generating customized insights.


---



## 🧮 M Language Example



Power Query M code used for grouping genres and loading structured data:



```m

Table.Group(#"Sorted Rows", {"Movie Title"},

{

    {"Combined Genre", each Text.Combine([Concat Genre], " / "), type text},

    {"AllData", each _, type table [

        Movie Title=nullable text,

        Release Date=nullable date,

        Wikipedia URL=nullable text,

        Concat Genre=nullable text,

        Director=nullable text,

        Actor First=nullable text,

        Actor Second=nullable text,

        Actor Third=nullable text,

        Actor Fourth=nullable text,

        Actor Fifth=nullable text,

        Budget ($)=nullable number,

        Box Office Revenue ($)=nullable number

    ]}

})
