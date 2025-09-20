# Shopping-Report-
# Why Metabase ? 
Metabase is a powerful, open-source business intelligence tool that empowers professionals to transform raw SQL queries into dynamic, interactive dashboards without the need for complex coding or design overhead. Its intuitive interface allows users to explore data visually, drill down into metrics, and share insights seamlessly across teams. For data analysts like Kazim, Metabase offers the flexibility to write custom SQL while also enabling rapid prototyping through its GUI, making it ideal for both technical deep dives and executive-level storytelling. Whether you're tracking purchase trends, visualizing seasonal patterns, or segmenting customer behavior, Metabase bridges the gap between data and decision-making with clarity and speed.

# Shopping Dashboard – Overview
🔍 Key Metrics & Insights
Total Purchase Amount: $233.1k
Category Distribution:
Clothing: 44.7%
Outerwear: 31.8%
Accessories: 15.5%
Footwear: 7.9%
Gender-Based Purchase Trends:
Female purchases dominate high-value items like dresses, handbags, and hoodies.
Male purchases lean toward jeans, shirts, and sweaters.
Seasonal Distribution:
Spring: 25.6%
Fall: 25.0%
Winter: 24.9%
Summer: 24.5%
Average Review Rating: ~3.75 across items
📊 Recommended Visuals
Insight	Chart Type	Rationale
Purchase Amount by Gender & Item	Clustered Bar Chart	Compare male vs female spending per item
Category Distribution	Donut Chart	Emphasize proportional breakdown
Seasonal Purchase Volume	Stacked Column Chart	Show item count per season
Item Ratings	Heatmap or Dot Plot	Spot rating consistency or outliers
🧠 SQL Snippet Example
sql
SELECT "gender", "item_purchased," AVG("purchase_amount_usd_") 
FROM "shopping_behavior_updated_20250918074934"
WHERE "purchase_amount_usd_" > 80
ORDER BY "purchase_amount_usd_" DESC;

# Shopping Dashboard – Purchase
🔍 Key Metrics & Insights
Total Previous Purchases: 98,871
Top Locations by Purchase Count:
California (95), Alabama (89), Arkansas (79)
Top Items by Purchase Amount:
Shorts, Hoodie, Sweater, Coat, Skirt, Sunglasses
Seasonal Trends:
Fall and Spring show slightly higher purchase volumes
Category Breakdown:
Clothing, Accessories, Footwear, Outerwear
Payment Methods Used: Credit Card, Debit Card, PayPal, Venmo, Cash, Bank Transfer
📊 Recommended Visuals
Insight	Chart Type	Rationale
Purchase Amount by Location & Item	Treemap	High-density comparison across states and items
Top 10 Items	Horizontal Bar Chart	Emphasize item popularity
Payment Method Distribution	Pie Chart	Show customer preference
Previous Purchases by Category	Column Chart	Compare volume across categories
🧠 SQL Snippet Example
sql
SELECT "location", SUM("purchase_amount_usd_") 
FROM "shopping_behavior_updated_20250918074934"
GROUP BY "location"
LIMIT 10;
