# SmartPrep-AI
AI-powered restaurant demand forecasting and food waste prevention prototype.
SmartPrep AI --- Restaurant Food Waste Prevention System
Project type: Business Analytics + AI prototype
Status: Academic prototype / proof of concept
# SmartPrep AI 🍃
### AI-Powered Demand Forecasting for Restaurant Food-Waste Prevention

**Project Type:** Business Analytics & Artificial Intelligence  
**Tools:** Orange Data Mining, Microsoft Excel, Lovable AI, GitHub  
**Project Focus:** Reducing avoidable food waste through data-driven food preparation planning

---

## 1. Project Overview

SmartPrep AI is an AI-powered restaurant operations prototype designed to help restaurants make better food preparation decisions by forecasting customer demand.

Restaurants often prepare food based on historical sales, estimated footfall, and staff experience. When actual demand is lower than expected, excess prepared food can result in food waste, unnecessary ingredient costs, and reduced profitability.

SmartPrep AI proposes a data-driven approach that uses machine learning to estimate order demand and convert those estimates into preparation recommendations. The system aims to help restaurant managers identify demand patterns, anticipate busy periods, and make more informed preparation decisions.

## 2. Business Problem Statement

**How can restaurants reduce avoidable food waste caused by over-preparation by using AI-powered demand forecasting and data analytics?**

The key challenge is deciding how much food to prepare before actual customer demand is known. Manual estimation can overlook differences between menu items, promotional periods, fulfilment centres, and special events.

SmartPrep AI addresses this challenge by combining demand forecasting, analytical visualisations, and a preparation-planning dashboard.

## 3. Industry Evidence

The importance of data-driven food waste prevention is reflected in industry reporting:

- **Restaurant India — How AI Is Helping Restaurants Reduce Food Waste:** Discusses how AI and data-informed planning can support food waste reduction in restaurants.  
  https://www.restaurantindia.in/article/how-ai-is-helping-restaurants-reduce-food-waste.16715

- **The Times of India — New course for restaurants: Analytics predict seasonal demand, limit food waste:** Reports on using analytics to anticipate seasonal demand and improve restaurant planning.  
  https://timesofindia.indiatimes.com/city/mumbai/new-course-for-restaurants-analytics-predict-seasonal-demand-limit-food-waste/articleshow/125379338.cms

- **ET HospitalityWorld — Leveraging AI/ML to drive cost reduction in the food service industry:** Discusses the potential of AI and machine learning in food service operations.  
  https://hospitality.economictimes.indiatimes.com/news/speaking-heads/leveraging-ai/ml-to-drive-cost-reduction-in-the-food-service-industry/107619205

These sources establish the relevance of the business problem and the potential role of analytics in improving restaurant operations.

## 4. Existing Process and Its Limitations

Restaurants commonly estimate preparation quantities using previous sales, expected footfall, staff experience, and safety margins.

However, this process has several limitations:

- Manual estimates may vary between managers and shifts.
- Simple averages may not capture changes in demand across different menu items.
- Promotions and special events can change order patterns.
- Excessive safety margins may increase over-preparation.
- Without systematic analysis, it is difficult to identify which meals or periods require different preparation strategies.

SmartPrep AI proposes a more consistent, data-informed approach to preparation planning.

## 5. Proposed AI Solution

SmartPrep AI combines machine learning with a manager-facing web application.

### Key Features

**1. Demand Forecasting**

Estimate expected orders using relevant information such as:

- Week
- Meal category
- Fulfilment centre
- Centre and region type
- Selling price
- Promotion status
- Discount percentage
- Special-event indicators

**2. Smart Preparation Planner**

Convert predicted demand into a suggested preparation quantity using a configurable safety buffer.

**3. Waste-Risk Alerts**

Highlight preparation plans that may require review because the planned quantity exceeds expected demand.

**4. Analytics Dashboard**

Display demand patterns across meals, promotions, and special-event periods.

**5. Manager Decision Support**

Provide managers with analytical recommendations while allowing them to review and adjust final preparation decisions.

## 6. Dataset and Methodology

The project uses a restaurant demand dataset containing **720 records**, covering 48 weeks, 3 fulfilment centres, and 5 meal categories.

The dataset includes variables such as:

- `Week`
- `Fulfilment_Centre_ID`
- `Centre_Type`
- `Region_Type`
- `Meal_Name`
- `Cuisine_Category`
- `Selling_Price_INR`
- `Promotion_Active`
- `Discount_Percent`
- `Special_Event_Week`
- `Orders`

The dataset also contains preparation, simulated overproduction, and shortage fields to support the preparation-planning demonstration.

The analysis combines machine learning model evaluation in Orange with descriptive analysis and visualisations in Excel.

## 7. Machine Learning Workflow in Orange

Two regression models were evaluated to predict `Orders`.

### Models Used

- **Linear Regression:** Provides a regression baseline for estimating order volume.
- **Random Forest Regression:** Models relationships between input features and order demand using an ensemble of decision trees.

### Workflow

1. **File:** Import the dataset.
2. **Select Columns:** Set `Orders` as the target and select the relevant demand-related input features.
3. **Linear Regression:** Train the baseline regression learner.
4. **Random Forest:** Train the tree-based regression learner.
5. **Test & Score:** Connect the dataset and both learners to the same widget to compare performance using five-fold cross-validation.

### Orange Results

The current Orange Test & Score output shows the following values:

| Model | MSE | RMSE | MAE | R² |
|---|---:|---:|---:|---:|
| Random Forest | 9.537 | 3.088 | 0.596 | 0.995 |
| Linear Regression | 0.000 | 0.000 | 0.000 | 1.000 |

Based on the displayed results, Linear Regression performs best in the current evaluation, with lower error metrics than Random Forest.

These results guide the model-selection decision for the prototype. Further testing on later weeks can help evaluate how well the selected model generalises to future demand.

## 8. Excel Data Analysis: Key Insights

Excel was used to summarise the dataset and create charts that connect the analysis to the proposed solution.

### Insight 1: Demand Varies by Meal Category

Average order volumes differ across the five meal categories. Biryani has the highest average demand in the dataset, while Salad Bowl has the lowest.

**Business implication:** Preparation recommendations should account for the specific meal rather than applying the same quantity rule to every menu item.

### Insight 2: Promotion Status Is Associated with Higher Average Orders

Average orders are approximately 139.3 when no promotion is active and 169.3 when a promotion is active in the dataset.

**Business implication:** Promotion status is a useful feature to consider when estimating demand and planning preparation quantities.

### Insight 3: Special-Event Weeks Show Different Demand Patterns

Average orders are approximately 145.1 during non-event weeks and 165.4 during special-event weeks.

**Business implication:** The forecasting system should consider special-event indicators so that managers can review preparation plans when demand conditions change.

These findings inform the meal selector, promotion input, event indicator, and demand visualisations included in the SmartPrep AI prototype.

## 📂 Project Files & Resources

All project resources used for the SmartPrep AI analysis and prototype are listed below.

| Resource | Description | Link |
|---|---|---|
| 📊 Excel Analysis & Charts | Dataset summaries, charts, and key business insights | [View Excel Analysis](https://github.com/SABIHA012/SmartPrep-AI/blob/75ea2c3426ab7941bb58b39b21a881581f460705/SmartPrep_AI_Analysis_and_Charts%20(1).xlsx) |
| 🧠 Orange Workflow | Machine learning workflow comparing Linear Regression and Random Forest | [Open Orange Workflow](https://github.com/SABIHA012/SmartPrep-AI/blob/7d67d9e8c8e9c4c9a9991f435860cd6597dcd2e5/ai%20cia.ows) |
| 🌐 Live Website | Interactive SmartPrep AI web application | [Visit SmartPrep AI](https://smartprep-kitchen-ai.lovable.app) |

### Tools Used

- **Orange Data Mining:** Machine learning workflow and model evaluation.
- **Microsoft Excel:** Exploratory data analysis, summary tables, and charts.
- **Lovable AI:** Web application prototype development.
- **GitHub:** Version control, project documentation, and resource sharing.
