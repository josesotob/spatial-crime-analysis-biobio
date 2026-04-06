# Spatial Analysis of Crime: Biobío Region (2023)

Applied geostatistical project using techniques from the mining industry—specifically spatial autocorrelation—to analyze urban safety. This study identifies statistically significant crime clusters in the Biobío Region of Chile using 2023 social crime data.

## Project Framework
The analysis was built using Python, leveraging **GeoPandas** for spatial data handling and **PySAL (esda)** for statistical testing.

---

## 1. Data Visualization: Choropleth Map
Before running statistical tests, I mapped the raw `F2023` crime data. This visual inspection shows a clear concentration of high-impact crimes in urban centers compared to rural areas.
<img width="1389" height="1267" alt="descargar" src="https://github.com/user-attachments/assets/c6a9c793-a25f-4269-a89b-df4fd75494bb" />

## 2. Global Spatial Autocorrelation (Moran's I)
To prove these patterns aren't just random, I calculated the Global Moran's I.

> **Analysis Note:** The result was a positive coefficient of **0.1097** ($p\text{-value} = 0.069$). This confirms a positive spatial trend: communes with similar crime rates are geographically clustered. I used a random seed of **99** to ensure these results are reproducible.
<img width="691" height="360" alt="descargar (2)" src="https://github.com/user-attachments/assets/466c0011-f50e-4b3e-9471-bca4b7f63c89" />


## 3. Local Clusters (LISA)
While the global test shows the overall trend, LISA identifies exactly where the "Hot Spots" and "Cold Spots" are.

| Cluster Type | Communes | Context |
| :--- | :--- | :--- |
| **HH (High-High)** | **Talcahuano, Laja, Cabrero** | **Hot Spots:** Areas with high crime surrounded by high-crime neighbors. |
| **LL (Low-Low)** | **Alto Biobío, Antuco, Quilaco** | **Cold Spots:** Statistically significant "safe zones." |
| **LH (Low-High)** | **Chiguayante, Tomé** | **Outliers:** Areas with low crime despite being in high-crime zones. |
| **HL (High-Low)** | **Mulchén** | **Outlier:** An isolated peak of high crime in a low-crime area. |


<img width="1389" height="1289" alt="descargar (3)" src="https://github.com/user-attachments/assets/c4de98c8-b5aa-4755-9cc3-3d7d3689e544" />


## Strategic Analysis of Crime Clusters

The data reveals a stark urban-rural divide. While the global trend remains moderate ($p = 0.069$), the local clusters in **Greater Concepción** and the **Los Ángeles** corridor are statistically robust and warrant specific operational attention.

### **Operational Insights & Resource Strategy**
From an optimization perspective, these results provide a quantitative roadmap for regional resource allocation:

> [!IMPORTANT]
> **1. Targeted Intervention**
> Security efforts and social programs should be prioritized in the **High-High clusters** (Talcahuano, Laja, and Cabrero). These areas represent the most concentrated crime loads in the region.

> [!TIP]
> **2. Staffing Efficiency**
> The **Low-Low coldspots** in the cordillera zone (Alto Biobío, Antuco) suggest that current security levels are effective. This data supports a strategic reallocation of personnel to higher-need urban zones without compromising safety in these low-incidence areas.

> [!NOTE]
> **3. Outlier Investigation**
> The cases of **Mulchén (HL)** and **Tomé (LH)** are geographic anomalies. These require further study to identify specific local variables—such as transit routes or localized economic shifts—that cause them to break the broader regional trend.

---
