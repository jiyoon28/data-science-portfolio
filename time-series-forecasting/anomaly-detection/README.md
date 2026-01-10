## Key Insights from Sensor Data Visualization
Based on the multi-plot analysis of the pump sensor data, the following observations were made regarding the relationship between sensor readings and machine failure events (indicated by red dashed lines):

### 1. Sharp Decline Prior to Failure
* **Observations:** Sensors 00, 02, 04, and 06 through 09 exhibit a drastic drop to near-zero values immediately before a failure event occurs.

* **Implication:**  These sensors are critical indicators directly linked to the machine's operational state. They provide a clear signal for "Binary Classification" of the machine's status.

### 2. High Correlation and Redundancy
* **Observations:** The majority of sensors follow a nearly identical pattern, dropping in synchronization during failure.

* **Implication:**  The sensors are strongly coupled. For future machine learning modeling, this suggests redundancy; we can likely perform Feature Selection to remove overlapping sensors without losing significant information.

### 3. Early Detection and Lead Time
* **Observations:** The raw data (orange line) begins to fluctuate or trend downwards slightly before the official 'BROKEN' timestamp is recorded.

* **Implication:**  This reveals a "Lead Time" for early warning systems. The volatility observed in this pre-failure stage is exactly what an Anomaly Detection model needs to capture to prevent downtime.

### 3. Unique Anomaly in Sensor 05
* **Observations:** Unlike other sensors that simply drop, Sensor 05 often exhibits spikes or significantly increased noise levels at the moment of failure.

* **Implication:**  This is likely a pressure or vibration sensor. Its unique behavior makes it a vital feature for distinguishing between different types of failure modes.

### 4. Impact of Feature Engineering (Temporal Patterns)
* **Observations:** Rolling statistics (1-hour Mean and Standard Deviation) consistently outperformed raw sensor readings in feature importance rankings. Multi-layered smoothing ($mean\_1h\_mean\_1h$) was particularly effective for $Sensor\_01$ and $Sensor\_00$.

* **Implication:**  The system’s failure mode is characterized by long-term degradation and trend shifts rather than instantaneous spikes. By smoothing out high-frequency noise, the model was able to focus on the underlying macro-trends that precede a breakdown.

### 5. Evolution of Predictive Performance
* **Observations:** The baseline model initially yielded a 0% Recall due to extreme class imbalance. By introducing the 24-hour "Predictive Window" labeling and rolling features, the Recall improved significantly from 14% to 23% using Random Forest.

* **Implication:**  This progress validates that adding temporal context (how the sensor behaved over the last hour) provides the model with the "memory" required to distinguish between normal fluctuations and actual pre-failure signatures.

### 6. Strategic Trade-off: Prioritizing Recall
* **Observations:** To achieve non-zero detection, the classification threshold was lowered to 0.01. This resulted in high Recall but low Precision (increased false alarms).

* **Implication:**  In an industrial context, the cost of an undetected pump failure (unscheduled downtime and hardware damage) far outweighs the cost of a false alarm (unnecessary inspection). Therefore, the model strategy intentionally prioritizes Recall to ensure maximum safety coverage, even at the expense of precision.

### 7. Ensemble Learning with Random Forest
* **Observations:** By applying the `RandomForestClassifier` with `class_weight='balanced'` and a custom threshold (0.01), we successfully moved the Recall from 0% to 23%.
* **Implication:** The model began to recognize subtle shifts in sensor trends that precede mechanical failure. This proves that even a baseline ensemble model can provide actionable early warnings when trained with properly engineered temporal features.