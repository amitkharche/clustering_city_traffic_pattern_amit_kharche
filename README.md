
---

# 🚦 City Traffic Pattern Clustering using KMeans

A machine learning solution to uncover **urban traffic patterns** by clustering areas based on traffic intensity, time, location, and weather. This helps **city planners and logistics providers** to optimize travel routes, manage congestion, and improve public transportation planning.

---

## Business Objective

In modern cities, traffic congestion leads to lost time, wasted fuel, and higher pollution. By clustering similar traffic patterns using historical data, we can:

* Identify traffic hotspots
* Optimize traffic signal timings
* Redesign public transport schedules
* Reduce emissions and travel time

This project uses **unsupervised learning (KMeans)** to cluster city traffic based on **speed, volume, time, and weather** factors.

---

## Dataset Overview

The dataset contains simulated traffic data with features such as:

* **Avg\_Speed**: Average vehicle speed in an area
* **Vehicle\_Count**: Total vehicles observed
* **Time\_of\_Day**: Morning, Afternoon, Evening, Night
* **Day\_of\_Week**: Weekday labels
* **Weather\_Condition**: Clear, Rainy, Foggy, etc.
* **Latitude & Longitude**: Geolocation of the traffic point

---

## Features Used

| Type            | Features                                              |
| --------------- | ----------------------------------------------------- |
| **Numerical**   | `Avg_Speed`, `Vehicle_Count`, `Latitude`, `Longitude` |
| **Categorical** | `Time_of_Day`, `Day_of_Week`, `Weather_Condition`     |

---

## ML Pipeline

### 1. **Preprocessing**

* Scale numerical features using `StandardScaler`
* Encode categorical features using `OneHotEncoder`
* Combine using `ColumnTransformer` pipeline

### 2. **Model Training**

* Apply **KMeans clustering** (with `n_clusters=5`)
* Use `silhouette_score` to evaluate the cluster quality
* Save both model and preprocessor for inference

### 3. **Streamlit App**

* Upload new CSV traffic data
* Predict cluster labels
* Visualize clusters using **PCA (2D reduction)**
* Download clustered results as CSV

---

## How to Run the Project

### Step 1: Clone the repository

```bash
git clone https://github.com/amitkharche/clustering_city_traffic_pattern_amit_kharche.git
cd clustering_city_traffic_pattern_amit_kharche
```

### Step 2: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 3: Train the KMeans Model

```bash
python model_training.py
```

This generates:

* `model/kmeans_model.pkl` – Trained clustering model
* `model/preprocessor.pkl` – Preprocessing pipeline

### Step 4: Launch Streamlit App

```bash
streamlit run app.py
```

Upload your traffic CSV → Get clusters → Visualize → Download results.

---

##  Project Structure

```
clustering_city_traffic_pattern_amit_kharche/
├── data/
│   └── simulated_city_traffic.csv        # Simulated input data
├── model/
│   ├── kmeans_model.pkl                  # Trained KMeans model
│   └── preprocessor.pkl                  # Fitted preprocessor
├── app.py                                # Streamlit app for UI
├── model_training.py                     # Model training and evaluation script
├── requirements.txt                      # Project dependencies
└── README.md                             # Project documentation
```

---

##  Requirements

```text
pandas
scikit-learn
streamlit
matplotlib
seaborn
```

*(Full list in `requirements.txt`)*

---

## 📈 Future Enhancements

* Integrate real-time traffic data APIs
* Use DBSCAN or Gaussian Mixture Models for advanced clustering
* Add SHAP explanations for feature influence on cluster behavior
* Deploy using Docker or FastAPI for production use

---

## 📄 License

This project is licensed under the **MIT License** – free for personal and commercial use.

---

## 📬 Contact

Want to collaborate or have questions?

* 🔗 [LinkedIn – Amit Kharche](https://www.linkedin.com/in/amit-kharche)
* 💻 [GitHub – @amitkharche](https://github.com/amitkharche)
* 📝 [Medium – @amitkharche14](https://medium.com/@amitkharche14)

---

