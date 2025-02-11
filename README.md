# Football Draw Prediction

## Overview
This is a **Football Draw Prediction** application built using **Tkinter**. It utilizes a **Poisson distribution** to estimate draw probabilities and determines potential betting recommendations based on bookmaker odds and calculated edge values.

The app:
- Predicts the probability of a football match ending in a draw.
- Uses **Poisson-based probability estimation** for goals.
- Compares bookmaker odds with computed probabilities to find value bets.
- Provides betting recommendations:
  - **Lay Bets (Edge < -7.0):** Uses the **Kelly Criterion** to determine stake.
  - **Back Bets (Edge > -2.0):** Uses a **flat stake of 1% of the account balance**.

---

## Features
✅ **Poisson-based goal prediction**  
✅ **Edge calculation for betting decisions**  
✅ **Dynamic stake sizing:**  
   - **Lay bets:** Uses **Kelly Criterion**
   - **Back bets:** Uses a **flat 1% stake**
✅ **Tkinter GUI for easy input & calculations**  
✅ **Reset button to clear input fields**  

---

## Installation
### Prerequisites
Ensure you have **Python 3.x** installed on your system.

### Install Required Libraries
This script relies on **Tkinter** (comes pre-installed with Python) and **math** (built-in). No additional dependencies are required.

```bash
pip install --upgrade pip  # Optional, to ensure the latest version of pip
```

### Running the Application
Clone this repository and run the script:

```bash
git clone https://github.com/yourusername/football-draw-prediction.git
cd football-draw-prediction
python draw_prediction.py
```

---

## Usage
1. **Enter match statistics** (average goals, injuries, form, position, bookmaker odds, etc.).
2. Click **"Calculate Draw Probability"** to compute probabilities and betting recommendations.
3. View the predicted draw probability, adjusted odds, edge calculation, and recommended stake.
4. Click **"Reset Fields"** to clear the input fields.

### Example Output
```
Draw Probability: 26.78%
Calculated Draw Odds: 3.73
Offered Draw Odds: 3.50
Adjustment Factor (Over/Under 2.5): 0.9214
Edge: -3.2784
Bet Type: No bet recommended
Recommended Stake: £0.00
```

---

## Logic Behind the Betting Strategy
### **1. Poisson Distribution for Goal Prediction**
The script calculates the likelihood of different match outcomes using the Poisson probability mass function:

\[ P(X=k) = \frac{e^{-\lambda} \lambda^k}{k!} \]

Where:
- \( \lambda \) is the expected goals scored.
- \( k \) is the number of goals.

### **2. Adjusting for Match Context**
- **Injuries** decrease team strength.
- **Form** and **league position** impact goal expectations.
- **Over/Under 2.5 market odds** are used to fine-tune probabilities.

### **3. Betting Criteria**
- **Lay Bets (Edge < -7.0):** Uses **Kelly Criterion** to size stakes.
- **Back Bets (Edge > -2.0):** Uses a **flat stake of 1% of account balance**.

---

