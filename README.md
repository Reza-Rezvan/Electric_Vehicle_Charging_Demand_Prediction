
# Electric Vehicle Charging Demand Prediction

This repository contains code and data for analyzing and predicting residential electric vehicle (EV) charging demand. Using data on plug-in electric vehicle recharging profiles, this project employs machine learning techniques to predict charging behavior with a focus on residential households.

---

## Data Description

The dataset includes in-home plug-in electric vehicle recharging profiles for 348 vehicles from 200 households, based on the 2009 Residential Energy Consumption Survey (RECS) data for the Midwest region of the United States. Each profile represents EV charging demand in watts, modeled at 10-minute intervals. 

### Key Characteristics:
- **Vehicles**: 60% are battery electric vehicles (BEVs) with a 200-mile range, and 40% are plug-in hybrid electric vehicles (PHEVs) with a 40-mile all-electric range.
- **Charging Type**: Level 1 charging (1920 W).
- **Data Format**: Profiles indicate total plug-in EV charging demand, aggregated at 10-minute intervals.

The data and model were derived using the methodology proposed by Muratori et al. in the research paper _"Highly-resolved modeling of personal transportation energy consumption in the United States."_ This dataset supports the forthcoming paper: _"Impact of uncoordinated plug-in electric vehicle charging on residential power demand."_ 

**Citation**:
```
Matteo Muratori, "Impact of uncoordinated plug-in electric vehicle charging on residential power demand - supplementary data, 2017. 
M. Muratori, M. J. Moran, E. Serra, and G. Rizzoni, “Highly-resolved modeling of personal transportation energy consumption in the United States,” Energy, vol. 58, no. 0, pp. 168–177, 2013.
```

---

## Project Overview

### Goals:
1. Analyze historical EV charging data to identify patterns and trends.
2. Generate lagged datasets to predict future charging demand.
3. Build and train an LSTM-based machine learning model to forecast charging demand with high temporal resolution.
4. Evaluate model performance using RMSE and R² metrics.

---

## Code Summary

### Data Preprocessing
- Imported raw data from an Excel file.
- Cleaned and reshaped the dataset for analysis and visualization.
- Generated lagged features (e.g., `EV_lag_1`, `EV_lag_2`, etc.) for time-series prediction.
- Resampled data at 4-hour intervals.

### Visualization
- Visualized data trends and pairwise correlations between households.
- Plotted time-series data for households to observe charging behavior.

### Model Building
- Preprocessed features using standard scaling techniques.
- Built an LSTM-based model to predict the next 4-hour EV charging demand using historical data.
- Trained the model for 100 epochs with a batch size of 1.

### Evaluation
- Calculated RMSE and R² scores for both training and test datasets.
- Visualized the predicted vs. actual values to assess model accuracy.

---

## Results

The LSTM model successfully predicts charging demand with a RMSE of **Train Score: X RMSE** and **Test Score: Y RMSE**. The evaluation metrics show the potential of deep learning in forecasting time-series data with high accuracy.

---

## Dependencies

- Python 3.8+
- Libraries:
  - pandas
  - numpy
  - matplotlib
  - seaborn
  - sklearn
  - keras
  - tensorflow

Install dependencies using:
```bash
pip install -r requirements.txt
```

---

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo-name.git
   ```
2. Place the `Residential-Profiles.xlsx` file in the root directory.
3. Run the analysis and model training script:
   ```bash
   python ev_charging_prediction.py
   ```

---

## Acknowledgments

This work is supported by:
- The National Science Foundation (Grant No. 1029337)
- U.S. Department of Energy (Contract No. DE-AC36-08GO28308)

Special thanks to G. Rizzoni, M. Moran, R. Sioshansi, B.-A. Schuelke-Leech, M. Roberts, J. Eichman, and A. Meintz for their contributions and valuable comments.

---

## License

This project is released under the MIT License. See `LICENSE` for more details.
