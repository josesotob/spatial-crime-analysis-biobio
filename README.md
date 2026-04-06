# 📍 Spatial Crime Analysis - Biobío Region (2023)

## 📖 Project Overview
This project applies geostatistical techniques—commonly used in **Mining Engineering** for ore grade estimation—to urban safety data. The goal is to identify statistically significant clusters of high-impact social crimes in the Biobío Region, Chile, using data from 2023.

---

## 🛠️ Technologies Used
* **Python 3.x**
* **GeoPandas:** For spatial data manipulation.
* **PySAL (esda):** For Moran's I and LISA statistics.
* **Matplotlib/Seaborn:** For data visualization.

---

## 📊 1. Global Spatial Autocorrelation (Moran's I)
We evaluated whether crime is randomly distributed or if it shows a geographic trend.

> **Note:** The analysis identified a positive Moran's I coefficient of **0.1097** ($p\text{-value} = 0.069$). 
> This indicates a positive spatial trend, suggesting that communes with similar crime 
> rates tend to be geographically clustered. A random seed of **99** was used for reproducibility.

---

## 🗺️ 2. Local Indicators of Spatial Association (LISA)
While Moran's I gives a global average, LISA identifies the specific "Hot Spots" and "Cold Spots."

| Cluster Type | Representative Communes | Description |
| :--- | :--- | :--- |
| **HH (High-High)** | **Talcahuano, Laja, Cabrero** | **Hot Spots:** Regional epicenters of criminal activity. |
| **LL (Low-Low)** | **Alto Biobío, Antuco, Quilaco** | **Cold Spots:** Statistically significant "safe zones." |
| **LH (Low-High)** | **Chiguayante, Tomé** | **Spatial Outliers:** Lower crime despite high-crime neighbors. |
| **HL (High-Low)** | **Mulchén** | **Spatial Outlier:** An isolated peak of high crime. |

---

## 💡 3. Discussion & Implications
The analysis reveals a clear urban-rural divide. Crimes are concentrated in **Greater Concepción** and the **Los Ángeles** corridor. 

* **Resource Optimization:** Policing and social programs should be prioritized in the HH clusters (Talcahuano, Laja).
* **Strategic Allocation:** The LL coldspot in the cordillera allows for more efficient staffing by reallocating personnel to higher-need areas.
* **Future Work:** Next steps include normalizing the data by population density (per capita rates) to refine the clustering results.
