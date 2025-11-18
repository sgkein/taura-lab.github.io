---
layout: page
title: Time-series forecasting
nav_exclude: true
---

## General Time Series Forecasting

Time series forecasting aims to predict the future evolution of signals that are ordered in time, such as electricity demand, stock prices, web traffic, environmental measurements, or sensor readings from complex systems. Compared with static prediction problems, time series forecasting must capture temporal dependencies, seasonality, long-term trends, and sudden regime changes, often under noisy and non-stationary conditions.

Modern research has moved from single-variable, short-horizon forecasts to **long-horizon, multivariate, and multi-domain** forecasting, where a single model must reason over long histories and provide reliable predictions across many datasets and application scenarios.

![](C:\Users\10205\Documents\GitHub\taura-lab.github.io\contents\img\time-series-forecasting.png)

------



## Spatio-Temporal Time Series Forecasting

Spatio-temporal forecasting studies how to predict future evolution of data that change **over time** and **across space**. Typical examples include traffic speed on road networks, passenger flow in public transport, energy demand in power grids, air quality in cities, and many other sensor-network signals.

Formally, we work with multivariate time series collected from many locations (nodes) connected by an underlying graph structure. The goal is to learn models that can forecast future values at all nodes, while capturing both:
- **Temporal dynamics** (daily/weekly patterns, rush hours, sudden changes), and  
- **Spatial dependencies** (how conditions at one location influence its neighbors).

![](C:\Users\10205\Documents\GitHub\taura-lab.github.io\contents\img\traffic.gif)

---

### Why Matters?

Time series forecasting underpins decision making in many industries where **the key question is “how will this quantity evolve over time?”** Typical applications include:

- **Finance and economics**  
  Predicting stock prices, volatility, macroeconomic indicators, and revenue helps institutions manage risk, allocate capital, and design trading or hedging strategies.

- **Energy and utilities**  
  Load and renewable generation forecasting are central to balancing supply and demand in power grids, integrating solar and wind power, and reducing operating costs while maintaining reliability. 

- **Retail, logistics, and operations**  
  Demand forecasting for products and services drives inventory planning, dynamic pricing, staff scheduling, and supply chain optimization, from e-commerce warehouses to call centers.

- **Healthcare and public health**  
  Time series models support hospital resource planning (e.g., emergency department visits or ICU occupancy) and epidemic surveillance, where forecasting patient volumes or infection curves enables proactive responses. 

- **Predictive maintenance and IoT systems**  
  Monitoring sensor streams from machines, vehicles, or infrastructure over time allows early detection of degradation and forecasting of failures, which reduces downtime and maintenance costs.

Overall, time series forecasting is a core tool for **anticipating future behavior from historical data**, turning large archives of temporal measurements into actionable planning signals.

---

- Spatio-temporal time series forecasting extends this perspective by asking **“how will the system evolve over time and across space?”** when data are collected from networks of locations (roads, sensors, regions). Representative applications include:

  - **Intelligent transportation systems**  
    Forecasting traffic flow, speed, and travel time on road networks supports congestion mitigation, route guidance, signal control, and demand-aware public transport planning. Spatio-temporal graph neural networks have become a key tool in urban computing for this purpose. 

  - **Air quality and environmental monitoring**  
    Spatio-temporal models predict pollution concentrations (e.g., NO₂, PM₂.₅, ozone) across cities or regions, combining time dynamics with spatial correlations between monitoring stations and emission sources. These forecasts are used for health risk assessment, environmental regulation, and urban planning. 

  - **Weather, climate, and hydrology**  
    Many geophysical processes, such as temperature, precipitation, and river discharge, are inherently spatio-temporal. Forecasting their evolution at multiple locations is crucial for flood warning, water resource management, and climate impact assessment.

  - **Urban analytics and smart cities**  
    Spatio-temporal data from traffic sensors, public transit, human mobility traces, and infrastructure monitoring enable forecasting of crowd flow, demand for shared mobility, or usage of urban services, supporting safer and more efficient city operations

  - **Agriculture and remote sensing**  
    Multi-temporal satellite or UAV imagery combined with ground sensors allows spatio-temporal models to predict crop yield, soil moisture, or vegetation stress at field or regional scale, informing precision agriculture and food security planning.

  In these scenarios, spatio-temporal forecasting is essential because **decisions depend not only on “when” but also on “where”**: which road segment will be congested, which neighborhood will experience high pollution, or which region will face resource shortages. Accurately modeling these patterns is central to building robust, data-driven urban and industrial systems.


---

### Problem Definition

Given $N$ spatially distributed sensors, at every timestep $t$, each sensor has a $C$‑dimensional observation $X\in\mathbb{R}^{C}$. For an input tensor $X^c\in\mathbb{R}^{T\times N\times C}$ = $X_{t-T+1:t}$ that contains the most recent $T$ steps, the forecasting task is to predict the next $T'$ steps for all nodes and channels:
$$
\begin{equation}
\widehat{X}_{t+1:t+T'}=F_{\theta}\!\bigl(X_{t-T+1:t}\bigr),\qquad 
F_{\theta}:\mathbb{R}^{T\times N\times C}\to\mathbb{R}^{T'\times N\times C}
\end{equation}
$$

where $F_{\theta}$ is a learnable spatio-temporal model parameterized by $\theta$. 

------

### Our Research Focus

Our research focuses on applying **deep learning methods to various-domain time series data and spatio-temporal time series data**. Concretely, we work on:

- **Accurate end-to-end spatio-temporal forecasting**
  - Developing end-to-end models (MLP, RNN/GRU/LSTM, graph neural networks, and Transformer-based architectures) that map raw historical sequences directly to future predictions.
  - Exploiting both temporal dynamics and spatial structure (e.g., road networks, sensor graphs) to improve short-term forecasting accuracy in urban traffic domain.
- **Scalable time series foundation models**
  - Building large-scale, pre-trained models for time series that can handle **many domains and datasets simultaneously**, including traffic, energy, finance, environmental monitoring, and other sensor streams.
  - Exploring scalable architectures to support long horizons, high dimensionality, and diverse domain forecasting.

------

### Related Papers:
[1] Li, Y., Yu, R., Shahabi, C. and Liu, Y., 2018, February. Diffusion Convolutional Recurrent Neural Network: Data-Driven Traffic Forecasting. In *International Conference on Learning Representations*.

[2] Wu, Z., Pan, S., Long, G., Jiang, J. and Zhang, C., 2019, August. Graph WaveNet for Deep Spatial-Temporal Graph Modeling. In *The 28th International Joint Conference on Artificial Intelligence (IJCAI)*. International Joint Conferences on Artificial Intelligence Organization.

[3] Bai, L., Yao, L., Li, C., Wang, X. and Wang, C., 2020. Adaptive graph convolutional recurrent network for traffic forecasting. *Advances in neural information processing systems*, *33*, pp.17804-17815.

[4] Gao, H., Jiang, R., Dong, Z., Deng, J., Ma, Y. and Song, X., 2024, August. Spatial-temporal-decoupled masked pre-training for spatiotemporal forecasting. In *Proceedings of the Thirty-Third International Joint Conference on Artificial Intelligence* (pp. 3998-4006).

[5] Dong, Z., Jiang, R., Gao, H., Liu, H., Deng, J., Wen, Q. and Song, X., 2024, August. Heterogeneity-informed meta-parameter learning for spatiotemporal time series forecasting. In *Proceedings of the 30th ACM SIGKDD conference on knowledge discovery and data mining* (pp. 631-641).

[6] Zhou, H., Zhang, S., Peng, J., Zhang, S., Li, J., Xiong, H. and Zhang, W., 2021, May. Informer: Beyond efficient transformer for long sequence time-series forecasting. In *Proceedings of the AAAI conference on artificial intelligence* (Vol. 35, No. 12, pp. 11106-11115).

[7] Liu, X., Liu, J., Woo, G., Aksu, T., Liang, Y., Zimmermann, R., Liu, C., Savarese, S., Xiong, C. and Sahoo, D., 2024. Moirai-moe: Empowering time series foundation models with sparse mixture of experts. *arXiv preprint arXiv:2410.10469*.

[8] Xiaoming, S., Shiyu, W., Yuqi, N., Dianqi, L., Zhou, Y., Qingsong, W. and Jin, M., 2025. Time-MoE: Billion-Scale Time Series Foundation Models with Mixture of Experts. In *ICLR 2025: The Thirteenth International Conference on Learning Representations*. International Conference on Learning Representations.