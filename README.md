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

## Clustering Methodology

### Household Segmentation
The system categorizes households into three distinct groups:

- **Cluster 0**: Low to moderate energy consumers
- **Cluster 1**: Moderate to high energy consumers  
- **Cluster 2**: High energy consumers with specific usage patterns

### Feature Analysis
The clustering considers multiple dimensions:
- Monthly energy consumption (kWh)
- Electricity bill amounts
- Household size and composition
- Regional location factors
- Income level indicators
- Appliance usage patterns
- Per-capita energy consumption

### Anomaly Detection
The system identifies unusual consumption patterns using:
- **Isolation Forest**: Detects outliers based on feature isolation
- **Autoencoder**: Neural network approach for pattern reconstruction
- **Consensus-based validation**: Combines both methods for reliable detection

## Output Structure

### Cluster Profiles
Each cluster receives:
- Size distribution and characteristics
- Typical consumption ranges
- Regional and demographic patterns
- Behavioral usage insights

### Anomaly Reports
- Flagged unusual consumption cases
- Severity scoring for each anomaly
- Feature contributions to anomaly detection
- Regional and temporal patterns

## Usage

### Input Requirements
- Household energy consumption data
- Appliance usage information
- Demographic and regional data
- Historical consumption patterns

### Output Delivery
- Labeled dataset with cluster assignments
- Anomaly detection flags and scores
- Cluster characteristic summaries
- Visualization-ready data formats

## Applications
- Targeted energy efficiency programs
- Customized tariff recommendations
- Regional energy planning
- Consumption pattern analysis
- Anomaly investigation and follow-up

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
