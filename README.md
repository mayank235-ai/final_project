# Real-Time Dynamic Parking Pricing System 

Hi, I'm **Mayank Mishra**, and this is my submission for a real-time dynamic parking pricing system — built entirely in Python using Google Colab, Pathway, and Bokeh.

The goal was to simulate and implement pricing strategies for urban parking lots based on live data like occupancy, queue lengths, traffic, and nearby competition. I’ve used **Pathway** for streaming data and **Bokeh** for plotting live price trends.

---

##  What This Project Covers

I built and compared three different models:

###  Model 1: Baseline Linear Pricing
A simple model where price increases proportionally with occupancy. It’s used as a reference for more intelligent models.

###  Model 2: Demand-Based Pricing
This model dynamically adjusts pricing based on:
- Occupancy rate
- Queue length
- Traffic conditions
- Special days (e.g., holidays)
- Vehicle type

###  Model 3: Competitive Pricing 
This model factors in nearby parking lots using their lat-long positions and adjusts prices based on competition.

---

##  Tech Stack

- **Python**
- **Google Colab** for development
- **Pathway** for real-time streaming simulation
- **Bokeh** for live visualizations
- **Pandas & NumPy** for data processing

---

## 📁 Project Structure

| File | Description |
|------|-------------|
| `final-project.ipynb` | Main notebook with all models & Bokeh plots |
| `final-project.csv` | Raw dataset simulating real-time parking data |
| `model1_output_stream.jsonl` | Output of Model 1 (streamed via Pathway) |
| `model2_output_stream.jsonl` | Output of Model 2 (streamed via Pathway) |
| `requirements.txt` | All packages used in the project |
| `README.md` | You’re reading it 🙂 |

---

##  Visualizations

All visualizations were made using Bokeh:
- Real-time pricing graphs for both models
- A comparison plot showing Model 1 vs Model 2
- Either animated or static based on performance

---

##  Assumptions

- Prices are bounded between ₹5 and ₹25.
- Demand is normalized between 0 and 1.
- Data is ingested in streaming mode (via Pathway) to simulate real-time scenarios.
- Vehicle type, traffic, and special day flags impact demand score in Model 2.

---

##  How to Run

1. Open `final-project.ipynb` in Google Colab
2. Upload `final-project.csv`
3. Install required packages:

```python
!pip install pathway==0.6.6 bokeh==3.4.1 pandas==2.2.2 numpy==1.24.4

4. Run all cells in order
5. Let Pathway stream the data and observe pricing in the Bokeh plots

##  Architecture Flow
flowchart TD
    A[📁 final-project.csv\nInput Data] --> B[ Pathway\nStreaming Ingestion]
    B --> C1[ Model 1 Logic\nLinear Pricing UDF]
    B --> C2[ Model 2 Logic\nDemand-Based UDF]
    C1 --> D1[ model1_output_stream.jsonl]
    C2 --> D2[ model2_output_stream.jsonl]
    D1 --> E[ Bokeh Plot\nModel 1]
    D2 --> E[ Bokeh Plot\nModel 2]
    E --> F[ Final Comparison Plot]


