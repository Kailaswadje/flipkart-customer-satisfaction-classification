### Objective
This project aims to classify **Customer Satisfaction Scores (CSAT)** using historical customer support interaction data. CSAT is a critical metric for evaluating service quality and customer experience. By analyzing past interactions, agent behavior, customer remarks, and ticket resolution times, we build a classification model to predict the level of customer satisfaction (1 to 5). This model will help proactively identify areas needing improvement and optimize support workflows.

---

### Dataset Overview
The dataset, `Customer_support_data.csv`, contains multiple entries from a customer support system. Each row represents a unique customer interaction along with metadata such as agent details, time of response, product details, and the final satisfaction score. The goal is to use these features to predict the **`CSAT Score`**, which ranges from 1 (very dissatisfied) to 5 (very satisfied).

---

### Feature-wise Explanation

- **Unique id**: A unique identifier for each customer support ticket. Used for tracking, not used in modeling.  
- **channel_name**: The communication channel used by the customer (e.g., Email, Chat, Phone), which influences response quality and time.  
- **category**: Broad classification of the support issue (e.g., Technical, Billing, Account), useful in understanding issue trends.  
- **Sub-category**: More specific issue label under each category (e.g., "Login Failure" under Technical) to capture granular insights.  
- **Customer Remarks**: Free-text input from customers about their issue; useful for sentiment analysis or NLP-based features.  
- **Order_id**: The ID of the order associated with the issue; may not be directly useful unless joined with order metadata.  
- **order_date_time**: Timestamp of the order; can be used to derive delays or time gaps relative to issue date.  
- **Issue_reported at**: Time when the customer reported the issue; helps calculate response and resolution delays.  
- **issue_responded**: Time when the support agent responded; combined with report time to calculate response duration.  
- **Survey_response_Date**: Date when customer gave the CSAT feedback; useful to understand follow-up timing, but not always predictive.  
- **Customer_City**: The city where the customer resides; can identify location-based trends or systemic issues.  
- **Product_category**: The type of product involved in the support ticket; some product types may result in higher or lower CSAT.  
- **Item_price**: Price of the item involved; higher prices might lead to higher customer expectations and affect satisfaction.  
- **connected_handling_time**: Total time spent by the agent resolving the issue; excessive durations may signal complexity or inefficiency.  
- **Agent_name**: Name of the support agent handling the ticket; can be encoded to understand individual performance impact.  
- **Supervisor**: The agent’s supervisor; useful to analyze team-level trends in CSAT.  
- **Manager**: The manager overseeing the support process; can help identify management-level influence on support quality.  
- **Tenure Bucket**: Agent experience group (e.g., 0–6 months, 6–12 months); more experienced agents might resolve issues better.  
- **Agent Shift**: Time shift during which the case was handled (e.g., Day, Night); night shifts might see different trends in CSAT.  
- **CSAT Score** *(Target Variable)*: Customer satisfaction score (1 to 5); the main variable we aim to classify using other features.

---

### Use Case
This classification model can be used by customer service teams to:
- Flag at-risk tickets likely to receive low CSAT scores.
- Identify factors leading to dissatisfaction.
- Guide training and resource allocation to improve service quality.
