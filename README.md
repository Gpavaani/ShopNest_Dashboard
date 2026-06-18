🛒 ShopNest Store — Sales Analysis Dashboard


Power BI Capstone Project | E-Commerce Sales Intelligence Dashboard built on 99,000+ real orders from a Brazilian online marketplace (2016–2018)




📊 Dashboard Preview

<img width="1287" height="695" alt="image" src="https://github.com/user-attachments/assets/6de13713-2040-4c14-928d-29c1c9f70ab8" />


🎯 Project Objective

Analyze ShopNest's e-commerce data to uncover sales trends, delivery performance, customer payment behaviour, and product ratings — all visualized in a single interactive Power BI dashboard.


📁 Dataset

FileDescriptionNexusgoods_orders_dataset.csv99,441 customer orders with timestamps & delivery datesNexusgoods_order_items_dataset.csvProduct-level line items with price & freightNexusgoods_products_dataset.csvProduct catalog with category namesproduct_category_name_translation.csvPortuguese → English category translationNexusgoods_order_payments_dataset.csvPayment method & value per orderNexusgoods_order_reviews_dataset.csvCustomer review scores (1–5)Nexusgoods_customers_dataset.csvCustomer location by stateNexusgoods_geolocation_dataset.csvLat/lng coordinates for map visuals

Time Period: September 2016 – August 2018

Source: Brazilian e-commerce marketplace (Nexusgoods / ShopNest)


📌 Key KPIs

MetricValue💰 Total RevenueR$ 16 Million📦 Total Orders99,441⏰ Delayed Orders8,117 (8.2%)⭐ Avg Review Rating4.09 / 5.0


📈 Dashboard Visuals & Questions Answered

1. 🏆 Top 10 Categories by Total Revenue

Horizontal bar chart showing the highest-grossing product categories.

Top category: Health & Beauty at R$1.4M, followed by Watches/Gifts and Bed/Bath/Table.

2. ⚠️ Delayed Orders by Category

Bar chart counting delayed orders (actual delivery > estimated delivery) per category.

Most delayed: Bed/Bath/Table (2,217 orders), Health & Beauty (2,045).

3. 📅 Monthly Delayed vs On-Time Orders

Clustered bar chart with line toggle comparing delayed and on-time deliveries month by month.

Includes drillthrough cross-report to view order-level delivery details.

Notable spike: November 2017 — 1,043 delayed orders during Black Friday.

4. 💳 Payment Method Analysis

Donut chart breaking down customer payment preferences.

Payment MethodTransactionsShareCredit Card76,79573.9%Boleto19,78419.0%Voucher5,7755.6%Debit Card1,5291.5%

5. ⭐ Product Rating Analysis

Two bar charts side by side — Top 10 highest-rated and Bottom 10 lowest-rated categories.


Highest rated: CDs/DVDs/Musicals (4.64), Fashion Children's Clothes (4.50)
Lowest rated: Security & Services (2.50), Diapers & Hygiene (3.26)


6. 🗺️ State-wise Sales Performance

Bar chart + map visual showing revenue concentration across Brazilian states.


São Paulo (SP): R$5.2M — 38% of total revenue
Rio de Janeiro (RJ): R$1.8M
Minas Gerais (MG): R$1.6M
Remote northern states (AP, RR, AC) account for under R$16K each


7. 📆 Seasonal Sales Patterns (Quarterly)

Line/area chart showing quarterly revenue trends from Q4 2016 through Q3 2018.

QuarterRevenue2016-Q4R$ 49K2017-Q2R$ 1.3M2017-Q4R$ 2.4M2018-Q2R$ 2.86M ← Peak


Revenue grew 57x in under 2 years, with Q4 seasonality driven by holiday demand.




🛠️ Tools & Technologies

Show Image
Show Image
Show Image


Microsoft Power BI Desktop — dashboard design & interactivity
DAX — calculated columns and measures
Power Query — data transformation and table relationships



🔗 Data Model

orders ──────────── order_items ──────────── products ──── category_translation
   │                     │
   ├──── payments         └──── reviews
   │
   └──── customers ──── geolocation

Key relationships all built on order_id and product_id as primary/foreign keys.


🧮 Key DAX Measures

dax-- Total Revenue
Total Revenue = SUM(order_items[price])

-- Delayed flag
Is_Delayed = IF(
    orders[order_delivered_customer_date] > orders[order_estimated_delivery_date],
    "Delayed", "On-Time"
)

-- Average Rating
Avg Rating = AVERAGE(order_reviews[review_score])

-- Year-Quarter label
Year_Quarter = FORMAT([order_purchase_timestamp], "YYYY") & "-Q" 
               & QUARTER([order_purchase_timestamp])


💡 Key Business Insights


Health & Beauty is the top revenue category but also has one of the highest delay counts — a supply chain opportunity.
Credit card accounts for nearly 3 in 4 transactions; optimising the checkout experience for card users could boost conversions.
São Paulo drives 38% of all revenue — targeted marketing in RJ and MG could unlock the next growth tier.
CDs/DVDs score the highest ratings (4.64) despite being a low-revenue category — an untapped upsell segment.
Black Friday (Nov 2017) caused the single largest delay spike — logistics planning ahead of festive seasons is critical.
Revenue grew 57x in under 2 years, confirming strong product-market fit and scaling potential.
