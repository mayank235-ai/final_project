# Real-Time Dynamic Parking Pricing System 🚗📊

Hi, I'm **Mayank Mishra** — and this is my final project submission for building a real-time, dynamic parking pricing system. 

In this project, I aimed to simulate how parking prices can be adjusted intelligently based on real-time conditions like traffic, queue lengths, special days, and vehicle types. I’ve used **Pathway** to stream data in a time-sensitive way and **Bokeh** to visualize how prices evolve as the situation changes.

---

## What This Project Covers

I built and compared 3 pricing models to understand how different strategies perform under real-time data:

###  Model 1: Baseline Linear Pricing
A simple model where the price increases linearly as occupancy increases. It's basic, but serves as a solid reference point.

###  Model 2: Demand-Based Pricing
A smarter model that adjusts pricing based on a custom demand function, considering:
- occupancy rate
- queue length
- traffic level
- whether it's a special day
- type of vehicle

This model feels more realistic and responsive to real-world signals.

###  Model 3: Competitive Pricing 
This one considers competitor lots nearby (using coordinates) and adjusts pricing accordingly. It's not required, but I added it to explore pricing under competition.

##  Tech Stack

This whole project runs in **Google Colab**, using:

- **Python**
- **Pathway** – for real-time data simulation and stream processing
- **Bokeh** – to create live visualizations
- **Pandas** and **NumPy** – for working with tabular data

## 📂 Project Files

| File | Purpose |
|------|---------|
| `final-project.ipynb` | The main notebook with all models and visuals |
| `final-project.csv` | Raw dataset used for simulation |
| `model1_output_stream.jsonl` | Streaming output from Model 1 |
| `model2_output_stream.jsonl` | Streaming output from Model 2 |
| `requirements.txt` | All packages needed to run the notebook |
| `README.md` | You're reading it :) |

##  Visuals Included

Using **Bokeh**, I created:
- Individual price trend plots for Model 1 and Model 2
- A comparison plot showing both models side-by-side
- Real-time-like behavior using animated (or static) price updates

##  Assumptions Made

- The data is simulated row-by-row using Pathway’s `mode="streaming"`.
- Demand-based pricing is capped between ₹5 and ₹25 for practical reasons.
- Some simplifications were made to ensure the notebook runs smoothly in Colab.
- Not all traffic or vehicle types are deeply modeled — just enough for logic simulation.

##  How to Run It Yourself

1. Open `final-project.ipynb` in Google Colab
2. Upload the dataset: `final-project.csv`
3. Install the dependencies:
   ```python
   !pip install pathway bokeh pandas numpy
4.Run cells in order — the models will stream data and generate price plots live.
5.Optional: Use the JSONL outputs to re-plot or compare models.
