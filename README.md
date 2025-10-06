# Energy-consumption-Models

## **1️ Supervised Learning (Your energy consumption predictor)**


* **Inputs:** Household info (size, income, region) + appliance details (power, usage hours, quantity).
* **Outputs / Predictions:**

  * Total kWh consumption
  * Estimated bill
  * Tariff bracket

** API:**

* `/predict` endpoint uses supervised learning.
* It predicts **how much electricity each appliance will consume**, the **total energy**, and **the bill**, based on what it learned from past data.
* If the ML model is not available, it falls back to **simple calculations using formulas**.

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
