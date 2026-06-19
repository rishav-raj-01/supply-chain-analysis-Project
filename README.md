# Supply Chain Analytics - Olist E-Commerce
A data analysis project exploring delivery performance, customer satisfaction, and logistics patterns across ~100,000 orders from Olist, a Brazilian e-commerce marketplace (2016-2018).

### **What this is about**
I got curious about how supply chain data actually looks in practice - not the clean textbook kind, but real orders with missing timestamps, cross-state shipments, and wildly varying freight costs. The Olist dataset from Kaggle was perfect for this.
The questions I set out to answer:

* How often do orders actually arrive late, and by how much?
* Which states have the worst delivery times, and is there a pattern?
* Does being late hurt review scores, and by how much?
* Is the delay coming from the seller or the carrier?


### **Dataset**
Seven relational CSV files from Kaggle, covering orders, customers, sellers, products, reviews, payments, and order items. Around 100k orders total, merged into a single working dataframe for analysis.

### **Tools used**
Python, Pandas, NumPy, Matplotlib, Seaborn - all inside a Jupyter notebook.

### **What I did**
* Cleaning: Filtered down to delivered orders only since other statuses had empty timestamp columns. Converted all datetime fields and dropped rows where delivery times were missing or came out negative.
* Feature engineering: Built delivery-related metrics from scratch - actual delivery days, estimated delivery days, delay (positive = late), seller processing time, carrier transit time, and a binary late flag. Also added freight ratio, same-state flag, order month, and hour/day-of-week columns.
* Merging: Joined all seven tables on order, customer, seller, and product IDs to get everything in one place.
### **Analysis sections:**

* Monthly order volume and revenue trend
* Delivery time distributions - actual vs. estimated vs. delay
* State-by-state delay rate and average delivery days
* Review scores broken down by how early or late the order arrived
* Seller processing time vs. carrier transit time split
* Order volume heatmap by day and hour
* Top product categories by revenue, volume, and delay rate
* Freight cost as a percentage of order value
* Payment type mix and installment patterns
* Correlation matrix across 11 supply chain variables
* Delay drivers - same-state vs. cross-state, product weight, seller processing speed quartiles


### **What I found**
The national delay rate sits around 8%, but northern states like AM, AP, and RR are hitting 12-18%. That's a pretty clear regional logistics problem, not random noise.
Olist estimates delivery at around 20 days on average, but actual delivery comes in around 12. The buffer is huge - probably intentional to protect review scores, but it might be hurting conversion.
Late delivery tanks reviews fast. On-time orders average 4.1-4.3 stars. Once you're more than 7 days late, you're dropping below 3. That correlation is strong enough that improving delivery consistency is basically the same thing as improving ratings.
About 35-40% of total delivery time comes from seller processing, not the carrier. That's the part the platform can actually control, which makes it the highest-leverage area to fix.
Small orders under R$50 are paying 30-40% of their order value in freight. That's a checkout conversion problem waiting to happen.

### Rishav Raj
