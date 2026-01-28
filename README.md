# Superstore Sales & Profitability Analysis
## Project Background & Overview

This project analyzes Superstore’s historical sales data to evaluate profitability drivers, loss-generating product segments, and regional performance disparities. While total revenue appears healthy, the objective of this analysis is to move beyond surface-level growth and identify where profit is created, where it leaks, and why.

### Business Questions:
- Which product category is both the best-selling and the most profitable?
- Which product sub-categories and specific products are top performers as well as those that are underperforming?
- How does profitability vary across regions, and which regions underperform relative to their sales contribution?
- How has the company's performance trended over recent months?
- Where can profitability be improved without increasing order volume or total sales?

  <img width="731" height="884" alt="database-relationship" src="https://github.com/user-attachments/assets/78b30198-17cc-469f-ad19-506743f5284e" />


## Executive Summary

Superstore generated __$2.30M in total sales, $286.4K in profit,__ across __5,009 orders__, resulting in an overall __profit margin of ~12.5%.__ While the business is profitable in aggregate, the profitability is unevenly distributed across products and regions.

From 2014 → 2017, performance scaled strongly: sales grew ~51.4% and profit grew ~88.6%, showing the business can grow profitably when it’s not undermined by margin erosion.

The core issue is profit quality and concentration:
- __20.4% of orders (1,022 / 5,009) are unprofitable.__
- Profit is extremely top-heavy: the __top 10% of orders generate ~98.9% of total profit__, while the bottom tail quietly cancels wins elsewhere.

The biggest controllable driver is discounting discipline:
- Once discounts reach roughly __30%+__, profitability flips negative and losses accelerate (especially in Furniture and parts of Technology). 
- Orders that contain __≥30% max discount__ make up __~20.4%__ of orders but drive __-$111.3K profit__ on __$556.0K sales__ (a clear profit leak).

__Technology and Office Supplies__ are the primary profit engines. In contrast, __Furniture significantly underperforms,__ with losses concentrated almost entirely in the __Tables__ sub-category.

From a geographic perspective, the __West and East regions__ contribute the majority of profits, while the __South and Central regions lag behind__, exhibiting weaker margins despite meaningful sales volume. This suggests that profitability issues are not demand-driven but rather linked to pricing strategy, discounting behavior, and product mix.

The analysis indicates that profitability can be materially improved without increasing sales volume by:

- Reducing exposure to consistently unprofitable products
- Tightening discount strategies, particularly in low-margin regions
- Redirecting marketing and sales focus toward high-margin categories and regions

  ![superstore-dashboard-snap](https://github.com/user-attachments/assets/b1e50681-5c16-4720-83cc-b88e256b5e0b)

## Key insights (deep-dive, stats-heavy)
__Overall: $2.297M sales, $286.4K profit, 12.47% margin, 5,009 orders.__

### Profit concentration:

- Top 10% of orders contribute ~98.9% of total profit.
- Top 1% contribute ~37.5% of total profit.
- Bottom 10% of orders alone lose ~$133.2K, forcing the rest of the business to “swim upstream” to stay positive.

Meaning: this is a classic “a few wins cover many leaks” situation - great for revenue optics, risky for long-term profitability.

### Discounting is the #1 profit leak (clear break point at ~30%)

Across all categories (margin by discount level):

- 0% discount: ~$1.088M sales, $321.0K profit, 29.5% margin
- 20% discount: ~$764.6K sales, $90.3K profit, 11.8% margin
- 30% discount: ~$103.2K sales, -$10.4K profit, -10.0% margin
- 40% discount: ~$116.4K sales, -$23.1K profit, -19.8% margin
- 70% discount: ~$40.6K sales, -$40.1K profit, -98.7% margin
- 80% discount: ~$17.0K sales, -$30.5K profit, -180% margin

![margin-by-category](https://github.com/user-attachments/assets/0e98e7f4-07a8-4ebc-bd60-5317d46e23e0)

Orders with max discount ≥ 30%:
- 1,020 orders (20.4%)
- $556.0K sales
- -$111.3K profit

Orders with max discount < 30%:
- 3,989 orders
- $1.741M sales
- $397.7K profit

### Product-level outliers drive a huge share of net profit (and loss)

Top profit product (single biggest contributor):
- Canon imageCLASS 2200 Advanced Copier: $25,199.93 profit on $61,599.82 sales (~40.9% margin)

Biggest loss products (consistent “margin traps”):
- Cubify CubeX 3D Printer Double Head Print: -$8,879.97 (≈ -80% margin)
- Lexmark MX611dhe Monochrome Laser Printer: -$4,589.97
- Cubify CubeX 3D Printer Triple Head Print: -$3,839.99

  ![biggest-loss-products](https://github.com/user-attachments/assets/3116df66-254a-4980-96b7-e79c332d34bb)

Pattern: many loss-leaders are high-ticket items sold at steep discounts, where “more sales” actually means “more loss.”

### Returns are meaningful, but not the primary driver

Returned orders: 296
Return rate: 5.91% 

Exposure tied to returned orders:
- $180.5K sales (≈ 7.86% of total sales)
- $23.2K profit (≈ 8.11% of total profit)

Return rate by category (unique-order basis):
- Technology: ~7.97%
- Furniture: ~7.71%
- Office Supplies: ~6.25%
