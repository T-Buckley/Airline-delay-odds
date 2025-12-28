# Airline-delay-odds
Airline Delay Odds
Project Overview

This project analyzes historical airline delay behavior to help assess the relative risk of flight delays under different conditions such as airline, route, and time of year.

The project originated from a real use case. I had an upcoming flight on an airline with a weaker on-time reputation and wanted a data-driven way to answer a simple question:

Based on historical performance, what is likely to happen to my flight?

Rather than attempting to predict exact delays, this dashboard surfaces observed delay rates and average delays that can be used to set expectations and compare airlines under similar conditions.

Data Source

Dataset: Carrier On-Time Performance

Source: Kaggle
https://www.kaggle.com/datasets/mexwell/carrier-on-time-performance-dataset/data

The dataset includes airline-level flight records with arrival delay, departure delay, cancellations, routes, and dates.

Tools Used

Power BI Desktop

DAX for measures and dynamic logic

Jupyter Notebook for initial exploration and validation

Key Questions Answered

How do arrival and departure delay rates differ by airline?

How does historical airline performance vary by route and season?

How reliable is the available data for a given filter selection?

How can recent data be prioritized without sacrificing statistical reliability?

Core Dashboard Features
Dynamic Analysis Window

To balance recency and sample size, the dashboard uses a dynamic analysis window:

Default window: last 5 years

If the number of valid flights drops below 50, the window automatically expands to 10 years

This approach ensures:

Recent performance is emphasized when sufficient data exists

Smaller airports or routes still produce meaningful results

The active analysis window is always displayed in the dashboard.

Valid Flight Definition

Not every flight record is suitable for delay analysis. A flight is considered valid if:

Airline, origin, destination, and month are present

Cancelled flights are included as valid flights

Non-cancelled flights must have both arrival and departure delay data

This prevents incomplete records from skewing delay metrics while still accounting for cancellations as part of overall airline reliability.

Metrics and Dimensions

All delay metrics are calculated per airline and respond to slicers for:

Origin airport

Destination airport

Month range

Key metrics include:

Arrival Delay percent by airline

Departure Delay percent by airline

Cancelled Flight percent by airline

Average Total Delay Minutes by airline

Aggregate KPI values across all airlines in the current selection

Interpreting the Results

The metrics shown represent historical averages and rates, not predictions. They are intended to:

Compare airlines relative to one another

Identify consistent delay patterns

Support expectation setting for future travel under similar conditions

This dashboard answers what has typically happened, which can be used as a proxy for what is likely to happen again under comparable circumstances.

How to Use

Select an origin airport

Optionally select a destination airport

Adjust the month range

Review airline-level delay metrics and overall KPIs

Note the active analysis window (5 or 10 years)

What This Project Demonstrates

Translating a real-world question into analytical logic

Designing consistent measures across tables, KPIs, and charts

Handling sparse data and edge cases such as cancellations

Using dynamic logic to adapt analysis scope automatically

Building a clean, interactive Power BI report for decision support

Files in This Repository

pbix or pbit: Power BI report or template

images: Dashboard screenshots

Notes

This project focuses on analytical clarity and interpretability rather than predictive modeling. The goal is to provide a transparent, defensible view of historical airline delay behavior that can inform real-world decisions.
