# 🧰 EV-PV Model – Training Section

## 📘 Introduction

The **EV-PV model** is designed to support decision-making and strategic planning for electric mobility within a given region. Initially developed within the [Citiwatts platform](https://citiwatts.eu/), the model has been transformed into a standalone tool, with expanded functionalities specifically adapted for Africa's transport and energy landscape.

EV-PV integrates multiple geospatial and technical components to:

- Analyze **passenger mobility demand**,
- Estimate **EV charging needs**,
- Evaluate the **potential of photovoltaic (PV)** energy to meet such needs,
- Determine **required charging infrastructure**.

The tool can function entirely on **open geospatial datasets**, making it particularly suitable for **data-scarce environments**. It supports various PV installation types, including **rooftop** and **free-standing** systems.

⚠ **Note on the African context**: Within the OM4A project, EV-PV model has undergone numerous updates to reflect African-specific transport modes, vehicle fleets, and data limitations.



## 🎯 Scope of the EV-PV Model

- **Objective**: Strategic planning of EV charging infrastructure and PV integration.
- **Platform**: Based on the open-source [Citiwatts](https://citiwatts.net) and originally from the ERANET OpenGIS4ET project.
- **Technological Scope**: Currently focused on **passenger cars**, the dominant road transport mode in Europe.
- **Geographical Scope**: Applicable globally, as long as data is available. Spatial resolution can reach **hectare-level granularity**.
- **Temporal Scope**: Data is analyzed primarily on a **daily** basis.




## 🔍 Model Features

EV-PV provides a modular workflow structured around three core features:

### 1. **EV Charging Demand Assessment**

- Calculates the **spatial distribution** of daily EV charging needs.
- Based on **population**, **mobility habits**, and **vehicle technical data**.
- Customizable by users to run **"what-if" analyses**.

🖼️ *Insert here: **``** - Daily charging demand map (example: Milano)*

```markdown
![Figure 9: Daily charging demand map](path/to/figure9.png)
```

### 2. **Charging Infrastructure Deployment**

- Determines the **density and optimal placement** of charging stations.
- Scenarios include **charging at home, work, and POIs**.
- Allows analysis of **PV-to-vehicle schemes** (PV-V), with other schemes (e.g., grid integration, vehicle-to-X) in development.

### 3. **Coupling with Photovoltaic (PV) Systems**

- Supports evaluation of **PV potential** to power EV infrastructure.
- Enables planning for **residential PV** and future grid-coupled systems.



## 🧾 Model Inputs and Outputs

🖼️ *Insert here: **``** - EV-PV Inputs and Outputs Diagram*

```markdown
![Figure 10: EV-PV Inputs and Outputs](path/to/figure10.png)
```

### 🔽 Key Inputs

1. **Demographic Data**: Population layers with high spatial resolution.
2. **Mobility Patterns**: Daily transport habits, region-specific.
3. **Vehicle Data**: Technical characteristics of local vehicle fleets.
4. **Geospatial Layers**: Roads, POIs, PV potential maps.

### 🔼 Key Outputs

- Maps of **EV charging demand** (in kWh/day or similar units).
- Optimized **locations of charging stations**.
- Evaluations of **PV coupling potential** (location-specific).



## 🌍 Relevance for Africa

In many African regions:

- **Private cars are not the primary mode of transport**,
- **Vehicle fleets and mobility behaviors differ** significantly,
- **PV deployment often includes off-grid and mini-grid systems**,
- **Data availability varies**, requiring modular and adaptive modelling.




## 🎥 Step-by-step Video Support

You can find all tutorials on <a href="https://www.youtube.com/playlist?list=PLHN93NPePQ1JPEb3YFsYi3TU__bb_Xcyx" target="_blank" style="text-decoration: none;">
  <img src="https://cdn.simpleicons.org/youtube/FF0000/16" alt="YouTube" height="16" style="vertical-align: text-bottom; margin-left: 4px;">
</a>

### ❓ Need Help?

Check our [Questions & Answers](docs/faq.md) page for common issues and guidance.
