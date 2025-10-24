# Product Conversion Funnel Analysis

This project analyzes the user conversion funnel for a large e-commerce store to identify the largest drop-off points and provide data-driven recommendations.

## Dashboard
<img width="1361" height="770" alt="Screenshot 2025-10-24 161731" src="https://github.com/user-attachments/assets/48734639-40b9-433e-b30e-ae6347e17ed5" />


---

## Data Source
The dataset used is the "E-Commerce Behavior Data from Multi-Category Store" available on Kaggle.
* **Link:** `https://www.kaggle.com/datasets/mkechinov/ecommerce-behavior-data-from-multi-category-store`
* **File Used:** `2019-Oct.csv` (42.4 million event records)

---

## Tools Used
* **Python (Pandas):** To process and analyze over 42 million event records.
* **Power BI:** To create the final dashboard visualizing the funnel and key conversion rates.

---

## Process
1.  **Data Loading:** Loaded the `2019-Oct.csv` dataset (42.4M rows) into a Pandas DataFrame, using `usecols` to only load the necessary `event_type` and `user_id` columns to save memory.
2.  **Data Processing:** Filtered the data for the three key funnel events: `view`, `cart`, and `purchase`.
3.  **Funnel Calculation:** Used Python `set()` operations to find the number of **unique users** who completed each sequential step (View -> Cart -> Purchase).
4.  **Data Export:** Exported the final aggregated 3-row summary table (`funnel_FINAL_for_powerbi.csv`) to be used in Power BI.
5.  **Visualization:** Built an interactive dashboard in Power BI to visualize the funnel and created DAX measures to calculate the two critical conversion rates.

---

## Key Findings & Recommendation

This analysis uncovered a critical insight into user behavior:

* **Finding 1: The "Browse" Problem**
    The largest "leak" in the funnel is at the very top. **Only 11.15%** of users who view a product ever add one to their cart. This means nearly 89% of all viewers drop off immediately.

* **Finding 2: The "Checkout" Success**
    Once a user *does* add an item to their cart, the checkout process is strong. **60.17%** of these users go on to complete a purchase.

### **Final Recommendation:**
The business should focus its efforts on **improving the "View-to-Cart" conversion rate**. The problem is not that users abandon their carts; it's that they never start one.

**Potential Strategies:**
* Implement better product recommendation algorithms.
* A/B test the "Add to Cart" button (e.g., size, color, placement).
* Introduce "limited-time offer" or "low stock" incentives to create urgency.
