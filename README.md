# Energy-consumption-Models

FastAPI = https://github.com/sergekamanzi/Energy-supervised-fastapi

video = https://youtu.be/mcohwHe89DU
## **1️ Supervised Learning (Your energy consumption predictor)**


* **Inputs:** Household info (size, income, region) + appliance details (power, usage hours, quantity).
* **Outputs / Predictions:**

  * Total kWh consumption
  * Estimated bill
  * Tariff bracket

API:

* `/predict` endpoint uses supervised learning.

---

## **2️ Unsupervised Learning (Clustering & anomaly detection)**

  1. **Clustering (K-Means / Rule-based):**

     * Groups households into **3 clusters** based on consumption:

       * Tier 1: Small families (20–99 kWh)
       * Tier 2: Average families (100–250 kWh)
       * Tier 3: Large families (300–600 kWh)
     * Helps **understand typical household usage patterns**.
  2. **Anomaly Detection (Isolation Forest / Rule-based):**

     * Finds households with **very unusual consumption** (e.g., over 600 kWh).
     * Flags them as anomalies for review.

**API:**

* `/api/unsupervised/cluster` → finds clusters of households
* `/api/unsupervised/analyze-stored` → finds anomalies and patterns in **all stored reports**
* Helps utilities or analysts **see trends, high-consumption households, and unusual usage**.


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
