# Southern-Perfecture-Restaurant

# Southern Prefecture - Data Insights

🌍 **Analyzing regional trends and economic development in the Southern Prefecture.** This project delves into economic data, population trends, and infrastructure developments in a specific region called "Southern Prefecture." The analysis includes population demographics, economic growth, and government investments in infrastructure projects.

🔍 **Explore the interactive visualizations and key metrics in the Power BI file.**

# Background

The Southern Prefecture project was initiated to provide insights into how the region is developing economically and socially. The main objective is to analyze regional trends, understand the effectiveness of government investments, and evaluate the progress of various infrastructure projects.

### Key Questions Addressed:
1. **What are the key demographic trends in the Southern Prefecture?**
2. **How is the local economy growing over time?**
3. **Which infrastructure projects are contributing the most to regional development?**
4. **What is the distribution of government spending across different sectors?**
5. **How do population trends correlate with economic growth?**

# Tools I Used

For this analysis, I utilized:
- **Power BI:** The primary tool for building interactive visualizations and performing detailed analysis on demographic and economic data.
- **DAX (Data Analysis Expressions):** Used for creating dynamic calculations and measures in Power BI.
- **M Code (Power Query):** For cleaning, transforming, and merging multiple data sources.
- **Conditional Formatting:** Applied to highlight critical metrics in the visuals, making important data stand out.

# The Analysis

### 1. Economic Growth Analysis
We focused on tracking the economic progress of the Southern Prefecture, highlighting key growth metrics such as GDP, employment rates, and investment in various sectors.
- **GDP growth over time**: Line charts showcasing the overall economic progress year by year.
- **Sector-wise contribution**: Pie charts visualizing how different industries contribute to the region's GDP.
- **Employment trends**: Heat maps showing employment rates across different districts.

### 2. Population Demographics
Population trends were analyzed to understand how demographic shifts affect economic growth. The analysis includes:
- **Age and gender breakdown**: Visualizations showing the population distribution by age group and gender.
- **Urbanization trends**: Insights into how the population is migrating from rural to urban areas, contributing to economic growth.
- **Population growth rate**: A time-based trend line showing the change in population over the years.

### 3. Infrastructure Development
The region has seen a significant rise in infrastructure investments, and this analysis covers:
- **Government spending**: Bar charts showing spending on key infrastructure projects, including transportation, healthcare, and education.
- **Project performance**: KPIs highlighting the most successful infrastructure projects and their impact on regional development.
- **Correlation with economic growth**: A scatter plot visualizing the relationship between infrastructure spending and GDP growth in the Southern Prefecture.

# DAX Code for Advanced Metrics

Some advanced DAX calculations were applied to create dynamic metrics:

- **Population Growth Rate**: This DAX formula calculates the year-over-year population growth rate.

```dax
Population Growth Rate YoY = 
VAR CurrentYear = YEAR(TODAY())
RETURN
    DIVIDE(
        SUMX(FILTER(Population, Population[Year] = CurrentYear), Population[Population Count]) 
        - SUMX(FILTER(Population, Population[Year] = CurrentYear - 1), Population[Population Count]), 
        SUMX(FILTER(Population, Population[Year] = CurrentYear - 1), Population[Population Count])
    )
```

This measure shows the percentage growth of the population year over year.

- **Government Spending Per Capita**: This DAX formula calculates the amount of government spending per person in the Southern Prefecture.

```dax
Government Spending Per Capita = 
DIVIDE(
    SUM(GovernmentSpending[SpendingAmount]), 
    SUM(Population[Population Count])
)
```

This measure provides insights into how much is being spent per person and helps assess the efficiency of government spending.

# M Code for Data Transformation

Before importing the data into Power BI, several **M Code** transformations were applied in Power Query:

- **Removing Duplicates**:

```m
= Table.Distinct(#"PreviousStep")
```

This ensures that there are no duplicate entries in the dataset, providing cleaner and more accurate data for analysis.

- **Appending Multiple Tables**:

```m
= Table.Combine({Table1, Table2})
```

Multiple datasets were appended together to create a unified view of the population and government spending data.

# Conditional Formatting

Conditional formatting was applied to highlight the most critical aspects of the data, including:
- **GDP Growth**: Cells with significant GDP growth (above 5%) were highlighted in **green**, while those with negative growth were marked in **red**.
- **Infrastructure Projects**: Projects with the highest ROI were marked in **blue**, while those underperforming were highlighted in **orange**.

```Power BI
In the "Format" pane, navigate to Conditional Formatting -> Based on the field value for each metric.
```

# Advanced Power BI Techniques

1. **Bookmarks for Dynamic Navigation**: Bookmarks were used to create dynamic navigation within the dashboard, allowing users to switch between different views (e.g., economic overview, infrastructure projects, and population trends) seamlessly.

```Power BI
View -> Bookmarks Pane -> Add Bookmark -> Define views for different pages
```

This allows for a more interactive experience, guiding users to explore different aspects of the dashboard.

2. **Drillthrough Filtering**: Drillthrough functionality was enabled, allowing users to click on a specific data point (e.g., a region or project) and be directed to a detailed page showing granular information about that selection.

```Power BI
Set up Drillthrough by right-clicking on a visual -> Drillthrough -> Add target pages for more details
```

This helps users dig deeper into specific data points to gather more insights without cluttering the main dashboard.

# What I Learned

🧩 **Advanced DAX Calculations:** Gained deeper insights into how to use DAX to calculate important metrics such as per capita spending and year-over-year population growth.

📊 **Power Query Data Transformation:** Mastered using M Code in Power Query to clean and transform data before loading it into the model, ensuring efficient data processing.

💡 **Interactive Power BI Features:** Learned how to implement advanced Power BI features like bookmarks and drillthrough filtering to create a more dynamic and user-friendly dashboard.

# Conclusions

### Key Insights:
1. **Economic Growth**: The Southern Prefecture has experienced significant economic growth, with certain sectors like healthcare and education showing the highest returns on investment.
2. **Demographic Shifts**: Population growth, especially urbanization, is closely linked to economic development, highlighting the importance of focusing on urban infrastructure.
3. **Effective Investments**: Government spending on infrastructure, particularly in education and healthcare, has had a profound positive impact on regional development.
4. **Interactive Insights**: Using bookmarks and drillthrough allowed for a more interactive and user-driven exploration of the dashboard.
