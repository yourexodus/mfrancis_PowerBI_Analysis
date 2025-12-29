Technical Documentation: 2023 Employment Analytics Dashboard
Project Objective
To analyze and visualize volatile shifts in US employment data (May–July 2023), specifically focusing on the Government sector's decoupling from broader economic trends.

Data Engineering & DAX
The primary challenge in this dataset was the non-chronological sorting of the "Month" field due to text-based naming conventions. I solved this by developing a custom DAX Calculated Column to facilitate chronological sorting.

DAX Formula for Sorting:

Code snippet

MonthDATE = 
VAR CleanText = 
    TRIM(
        SUBSTITUTE('establishement_data'[Month], "(p)", "")
    )
VAR YearNum = 
    VALUE(RIGHT(CleanText, 4))
VAR MonthNum = 
    MONTH(
        DATEVALUE(
            LEFT(CleanText, 3) & " 01 2000"
        )
    )
RETURN
DATE(YearNum, MonthNum, 1)
Visual Strategy & Analysis
Waterfall Chart: Used to display Cumulative Change. This highlights how the Government sector grew by nearly 100k total over the period rather than just showing monthly snapshots.

Line Chart (High/Low Points): Integrated data labels for peaks (57k in June) to provide immediate context for executive stakeholders.

Clustered Column Chart: Provided a sectoral comparison to validate that the Government surge was an outlier compared to Durable Goods and Leisure & Hospitality.

Key Insights Delivered
Isolated Volatility: Identified that the Government sector experienced massive, isolated fluctuations that did not correlate with the rest of the economy.

Growth Leader: Pinpointed June 2023 as the peak growth period, contributing over 50% of the quarter's total expansion.

Why this helps you with recruiters:
Transparency: You are showing them the "Engine" (the DAX code) behind the pretty charts.

Communication: You are translating technical steps (cleaning data) into business outcomes (delivering insights).