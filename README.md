# Bike Share Price Analysis and Dashboard
**Business Task**: This project involves developing a dashboard for a fictional bike share company that displays their key performance metrics to inform their financial decision making. The data is over 2 years and provided by the company.

**Technologies**: SQL Server, Power BI, Microsoft Excel
## Process
* Clean and prepare data using data checks like checking for nulls, duplicates
* Use CTE's and select statements to format SQL query that includes appropriate data
  * ```
    with get_cte as (
    SELECT * from bike_share_yr_0
    union all
    SELECT * from bike_share_yr_1)
    ```
  * ```
    select
    dteday,
    season,
    a.yr,
    weekday,
    hr,
    rider_type,
    riders,
    price,
    COGS,
    riders*price as revenue,
    riders*price - COGS as profit
    from get_cte a
    left join cost_table b
    on a.yr = b.yr
    ```
* Perform calculations to answer business task
  * ![excelscreenshot](https://github.com/user-attachments/assets/7dea1829-1a96-4afb-bd2c-c8f1674a3e0c)
* Format results in Power BI in visually pleasing and informative way
## Recommendations
* Price-setting Recommendations:
  * According to the data, a slight to moderate price increase for the service could be a way to test the market response without risking a significant loss in users. A 10-15% increase as opposed to the 25% increase from 2021-2022 would set the price at $5.49 to $5.74.
* Future Recommendations:
  * Market Analysis: Conduct further market research to better understand customer satisfaction and the overall state of the economy. This can inform the relatively unusual positive price elasticity that was determined from the data, and prevent any overcorrections in pricing.


Dashboard: ![dashboardscreenshot](https://github.com/user-attachments/assets/0ebcaf57-ab6a-4b51-b712-c8903ad0f56a)
