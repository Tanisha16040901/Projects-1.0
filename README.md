# Food Delivery Marketplace Optimization: FoodHub Data Analysis 📊🍲

## Project Context
The food delivery market in New York is rapidly expanding, with students and busy professionals relying heavily on delivery platforms due to demanding lifestyles. FoodHub is a food aggregator company that offers users seamless access to multiple restaurants through a single smartphone app.

The platform handles the complete order cycle: matching customers with restaurants, orchestrating delivery logistics via a dedicated fleet, collecting customer ratings, and generating revenue by collecting a fixed margin from each completed order.

## Project Objective
As a Data Scientist, the goal of this project is to analyze the historical transaction and delivery logs stored by FoodHub. By evaluating demand patterns, operational fulfillment windows, and customer satisfaction metrics, this analysis provides actionable, data-backed strategic insights to optimize the marketplace framework, boost platform efficiency, and enhance user experience.

## Data Dictionary
The dataset encapsulates full transactional data points for each order:
- `order_id`: Unique identifier of the order.
- `customer_id`: Unique identifier of the customer.
- `restaurant_name`: Name of the restaurant vendor.
- `cuisine_type`: Category of cuisine ordered.
- `cost`: Total cost of the individual order (USD).
- `day_of_the_week`: Contextual placement of the order (Weekday vs. Weekend).
- `rating`: Customer satisfaction rating scored out of 5 (or 'Not given').
- `food_preparation_time`: Core kitchen turnaround time (from restaurant confirmation to driver pickup, in minutes).
- `delivery_time`: Logistics transit window (from driver pickup to drop-off confirmation, in minutes).

## Tech Stack
- **Language:** Python 3.x
- **Libraries:** Pandas, NumPy, Matplotlib, Seaborn

See `requirements.txt` for exact packages.

## Key Metrics
Based on 1,898 orders from 1,200 unique customers across 178 restaurants and 14 cuisine types:

- **Order volume:** 1,351 weekend orders vs. 547 weekday orders — weekends drive ~2.5x weekday demand.
- **Cost:** average order $16.50 (range $4.47–$35.41); 29.24% of orders (555) are above $20.
- **Timing:** average food preparation time is 27.4 min (20–35 min range), average delivery time is 24.2 min (15–33 min range); 10.54% of orders (200) take over 60 minutes total.
- **Weekday vs. weekend delivery:** 28.34 min average on weekdays vs. 22.47 min on weekends — a 5.87 min gap, likely traffic-driven.
- **Ratings:** 736 of 1,898 orders (38.8%) have no rating; among rated orders the average is 4.34/5.
- **Top restaurants by volume:** Shake Shack (219 orders), The Meatball Shop (132), Blue Ribbon Sushi (119), Blue Ribbon Fried Chicken (96), Parm (68).
- **Most popular weekend cuisine:** American (415 orders).
- **Promo-eligible restaurants** (>50 ratings, average rating >4): Shake Shack, The Meatball Shop, Blue Ribbon Sushi, Blue Ribbon Fried Chicken — also the top estimated revenue generators under FoodHub's tiered commission structure.

## Key Insights & Actionable Business Recommendations
1. **Demand and Visibility Mapping:** High-demand cuisines and top-performing cluster vendors (e.g., Shake Shack) should be prioritized via premium featured listings or dynamic advertising during peak operational hours to maximize marketplace transaction volume.
2. **Systemic Feedback Enhancements:** To address data gaps caused by a high volume of unsubmitted ("Not given") customer feedback, the platform should introduce user engagement mechanics (such as a point-accumulation or gamification reward loop) to stabilize data ingestion for recommendation engines.
3. **Logistical Strategy:** Correlate total transit metrics (`food_preparation_time` + `delivery_time`) against regional customer retention levels to identify operational choke points and optimize delivery-partner driver routing.

## How to Run
1. Install dependencies: `pip install -r requirements.txt`
2. Ensure `foodhub_order.csv` is in the same directory as the notebook
3. Run `FDS_Project.ipynb` top to bottom
