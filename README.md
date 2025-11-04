# Energy-consumption-Models

FastAPI digital ocean = https://seahorse-app-8xk3k.ondigitalocean.app/docs

landingpage = https://powerlytics-ui.vercel.app/

dashboard = https://github.com/sergekamanzi/Energy-Consumption-Dashboard

backend = https://github.com/sergekamanzi/energy-consumption-server_side

video for the models = https://youtu.be/mcohwHe89DU

video for the UI = https://www.youtube.com/watch?v=BI6lLXLXFpY

## **1️ Supervised Learning (energy consumption predictor)**


* **Inputs:** Household info (size, income, region) + appliance details (power, usage hours, quantity).
* **Outputs / Predictions:**

  * Total kWh consumption
  * Estimated bill
  * Tariff bracket

API:

* `/predict` endpoint uses supervised learning.

---

## **2️ Unsupervised Learning (Clustering & anomaly detection)**

###  Clustering with K-Means

**What it does:**
- Groups households into 3 distinct consumption profiles
- Identifies natural patterns in energy usage behavior
- Creates customer segments for targeted recommendations

**Household Clusters:**
1. **Low Consumption Households** - Minimal energy usage, typically smaller families
2. **Medium Consumption Households** - Balanced usage across essential appliances  
3. **High Consumption Households** - Large households or high-energy appliance users

**Features Analyzed:**
- Monthly energy consumption (kWh)
- Bill amounts and tariff brackets
- Household size and demographics
- Regional patterns and income levels
- Appliance usage intensity

###  Anomaly Detection with Isolation Forest

**What it does:**
- Identifies unusual consumption patterns automatically
- Flags households that deviate from normal behavior
- Detects potential issues like faulty appliances or unusual usage

**Anomaly Indicators:**
- Extremely high energy consumption
- Unusual bill amounts for household characteristics
- Abnormal per-capita consumption
- Regional consumption outliers

###  Business Applications

**For Energy Providers:**
- Targeted energy efficiency programs
- Customer segmentation for personalized services
- Early detection of unusual consumption patterns
- Resource planning based on consumption clusters

**For Households:**
- Personalized energy-saving recommendations
- Understanding consumption relative to similar households
- Early detection of potential appliance issues
- Budget planning based on cluster benchmarks

### How to Use

1. **Generate Reports** - Create household energy predictions first
2. **Run Analysis** - Click "Run AI Analysis" in Admin section
3. **View Clusters** - See household segmentation results
4. **Check Anomalies** - Review flagged households for investigation
5. **Get Insights** - Access business recommendations and patterns

###  Technical Implementation

- **Clustering**: K-Means algorithm with feature scaling
- **Anomaly Detection**: Isolation Forest with automatic thresholding
- **Batch Processing**: Analyze multiple households simultaneously
- **Real-time Analysis**: Instant results with model explanations
---

## **3 Time Series**

- Purpose: forecast next 1–2 months of household energy use from monthly history (>= 3 values).
- Models: LSTM (primary) with SARIMA fallback; bill and tariff computed with Rwanda rates.
- Files: `timeseries/individual_household_lstm_model.h5`, `timeseries/sarima_model.pkl` (+ optional scalers).
- Endpoint: `POST /api/timeseries/forecast` → returns per‑month kWh, bill, and tariff bracket; horizon capped at 2.

---

## Setup Instructions

1. Activate Python Environment
   Make sure you have your Python virtual environment ready. To activate it, run:  
   bash
   .\env-supervised\Scripts\Activate


2. Install Dependencies
   If you already have a `requirements.txt` file, install all dependencies using:

   bash
   pip install -r requirements.txt
   

3. Run the API
   Start the FastAPI server with the following command:

   bash
   uvicorn main:app --reload --host 0.0.0.0 --port 8000


4. Swagger UI
   Once the server is running, you can access the interactive API documentation (Swagger UI) at:
  (http://127.0.0.1:8000/docs)

5. Freeze Dependencies
   To save your current environment packages, run:

   bash
   pip freeze > requirements.txt
