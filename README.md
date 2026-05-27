Table of Contents

Project Overview
Business Problem
Tools Used
Dataset
Project Workflow
Key Findings
Business Recommendations
Key Learnings


Project Overview
This project analyses 1,200 social media posts published by FreshWear — a fictional D2C clothing brand based in India — across Instagram, Facebook, YouTube, Twitter/X and LinkedIn over the period January 2023 to December 2024.
The analysis moves beyond surface-level average ROAS reporting to uncover hidden inconsistencies in campaign performance, identify the root cause of budget inefficiency, and deliver a data-backed budget reallocation recommendation.

Business Problem:

FreshWear increased its social media ad spend by 40% in 2024. Despite this, revenue growth did not scale proportionally. All campaigns appeared to show healthy average ROAS of 3x–4x, making it difficult to identify where the budget was actually working and where it was being wasted.

Core question: Which platforms, campaigns, and content types are genuinely driving revenue — and where should the budget be reallocated?

Tools Used
ToolPurposePostgreSQL (pgAdmin)Data cleaning, KPI extraction, ROAS variance analysisMicrosoft ExcelDeep-dive analysis, outlier impact quantification, budget reallocation modelPower BIExecutive dashboard, ROAS inconsistency deep dive, visual storytelling

Dataset
The dataset was purpose-built for this analysis and contains 1,200 posts with 21 columns including:

Platform, Content Type, Campaign, Region
Reach, Impressions, Engagements (Likes, Comments, Shares, Saves)
Clicks, Video Views, New Followers Gained
Ad Spend (₹), Revenue Generated (₹)
Sentiment (Positive / Neutral / Negative)

Brand: FreshWear (fictional D2C clothing brand, India)
Period: January 2023 — December 2024
Platforms: Instagram, Facebook, YouTube, Twitter/X, LinkedIn
Campaigns: 8 paid campaigns + Organic

Project Workflow
Phase 1 — SQL: Data Cleaning & KPI Extraction

Profiled data for nulls, duplicates and date range validity
Calculated engagement rate by platform
Computed campaign-level ROAS and flagged underperformers
Analysed content type performance by platform
Built monthly trend analysis with month-over-month growth
Compared organic vs paid post performance
Key addition: Measured ROAS standard deviation at post level within each campaign to detect inconsistency hidden behind healthy averages

Phase 2 — Excel: Deep-Dive Analysis

Built master KPI summary sheet including ROAS stddev as a core metric
Created campaign comparison table with average ROAS and stddev side by side
Built outlier impact analysis (XL03) quantifying the effect of POST_0622
Developed budget reallocation model (XL05) with projected revenue uplift

Phase 3 — Power BI: Executive Dashboard
Built a 2-page interactive dashboard:
Page 1 — Executive Overview
KPI banner, platform performance bar chart, revenue vs spend trend line, content type donut chart, slicers for Year, Platform and Campaign
Page 2 — ROAS Inconsistency Deep Dive
Campaign stddev bar chart, outlier spotlight card, with vs without outlier KPI cards, platform × content type ROAS heat matrix, budget reallocation clustered bar chart with revenue uplift KPI

Key Findings
Finding 1 — Average ROAS Was Hiding the Real Problem
All campaigns showed average ROAS between 3x–4x, which appeared healthy. However when ROAS standard deviation was measured at the post level, two campaigns stood out as dangerously inconsistent:
Campaign Avg ROAS ROAS Stddev Verdict Summer Collection Launch 4.28x  5.74 Highly inconsistent Winter Warmers~3.8x  5.60  Highly inconsistent Back to College~3.2x  1.20 Stable — benchmark New Year New Look~3.1x 1.37 Stable respectively.
Finding 2 — One Post Was Deceiving the Entire Campaign
Summer Collection Launch's inconsistency was traced to a single outlier post:
Metric With Outlier Without Outlier Difference Summer Launch Avg ROAS 4.28x  3.66x  0.62 Summer Launch ROAS Stddev 5.74  1.26 4.48 Thread Content Avg ROAS 4.60x  3.56x  1.03 Thread Content ROAS Stddev 7.96 1.09 6.87 respectively
POST_0622 — a single Twitter/X Thread post — generated ₹1,948 revenue from just ₹30.64 in spend, producing a ROAS of 63.59x. This one viral post was single-handedly inflating the campaign average and driving the stddev to 5.74. Without it, Summer Collection Launch is actually a stable, average-performing campaign — comparable to Back to College.
Finding 3 — Thread Content Is a False Signal
Twitter/X Thread content showed the highest average ROAS of 4.60x across all content types — suggesting FreshWear should invest more in Threads. However this was entirely caused by POST_0622. The realistic repeatable ROAS for Thread content is 3.56x — decent but not exceptional. FreshWear was making budget decisions based on a non-repeatable result.
Finding 4 — Facebook Video Has a Real Inconsistency Problem
Unlike the Thread situation which was a statistical outlier, Facebook Video under Summer Collection Launch showed genuine inconsistency with stddev of 6 even after removing POST_0622. This indicates a real operational issue — inconsistent creative quality, targeting, or audience strategy — that needs to be fixed before scaling.

Business Recommendations
1. Adopt ROAS Stddev as a Mandatory KPI
Average ROAS alone is insufficient for budget decisions. ROAS standard deviation must be tracked alongside average ROAS in all campaign performance reviews. A campaign with high average ROAS but high stddev is riskier than a stable campaign with moderate average ROAS.
2. Reduce Thread Content Paid Spend by 50%
The realistic repeatable ROAS for Thread content is 3.56x — not the inflated 4.60x seen in reporting. Reduce paid investment in Twitter/X Threads and reallocate to stable high-performing format combinations.
3. Audit and Fix Facebook Video Before Scaling
Do not increase Facebook Video budget until creative and targeting consistency is resolved. Benchmark high-performing Facebook Video posts against low-performing ones and standardise the approach.
4. Use Back to College as the Campaign Blueprint
Back to College delivers 3x+ ROAS with stddev of 1.2 — the ideal combination of strong returns and consistency. Its content mix, posting frequency and creative approach should be documented and used as the internal standard for planning future campaigns.
5. Flag Outlier Posts Automatically in Reporting
Any post delivering ROAS above 10x should be flagged as an outlier and excluded from campaign performance averages. These posts should be studied for virality insights but must never be used to justify budget allocation decisions.
6. Reallocate Budget to Stable High-ROAS Combinations
Shift spend away from inconsistent formats toward platform and content type combinations that show ROAS above 3x and stddev below 2. These combinations deliver predictable, scalable returns.

Key Learnings

Averages can lie. A healthy average ROAS masked a significant budget efficiency problem that only became visible when consistency was measured alongside magnitude.
One data point can distort everything. POST_0622 demonstrates how a single viral event can mislead strategic decisions if outlier detection is not built into reporting.
Root cause analysis requires going deeper than the first answer. The real finding was not that campaigns had different ROAS — it was that one post within one content type within one campaign was responsible for almost all the observed inconsistency.
Business recommendations must be specific and quantified. Saying "improve campaign performance" is not a recommendation. Identifying exactly which format to cut, which to scale, and projecting the revenue impact is.


Dataset generated for analytical purposes. FreshWear is a fictional brand created to simulate realistic D2C marketing analytics scenarios.
