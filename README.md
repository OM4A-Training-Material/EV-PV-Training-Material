# 🚗 EVPV-simulator

## 📚 Documentation & Training Material

The **EVPV-simulator** (Electric Vehicles – PhotoVoltaics Simulator) is an open-source Python tool developed at EPFL PV-LAB to simulate the spatial and temporal charging needs of privately owned electric vehicles (EVs) and match them with local solar photovoltaic (PV) generation. Designed for urban environments with limited mobility data, it combines georeferenced datasets with spatial trip distribution models and uses [PVLib](https://pvlib-python.readthedocs.io/en/stable/) for solar generation modeling.

- 📖 [**Full Documentation**](https://evpv-simulator.readthedocs.io/en/latest/): User guide, API, and workflow documentation
- 💻 [**Project GitHub**](https://github.com/evpv-simulator): Access source code and examples
- 🐍 Language: Python 3.12

---

## 🧠 Model Overview

The EVPV-simulator provides three key simulation outputs:

1. **Mobility Demand Estimation** – Using population density, workplace, and POI data, it divides the city into traffic zones and simulates home-to-work commuting patterns.
2. **Charging Demand Calculation** – Based on vehicle parameters, SoC logic, and user-defined charging habits (home, work, POIs), the model estimates zone-level and hourly charging needs.
3. **EV–PV Complementarity** – Calculates hourly PV production using PVLib and evaluates self-consumption/self-sufficiency based on spatial-temporal match with EV charging.

<img src="model_overview_3.png" width="100%">
<p><font size="-1">🔁 EVPV-simulator overview – Not all inputs/outputs shown.</font></p>

---

## ⚙️ Installation

### 🐍 Python Setup

We recommend using **Miniconda**:
- Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) and create a virtual environment:

```bash
conda create --name evpv-env python=3.12
conda activate evpv-env
```

### 📦 Install EVPV-simulator

```bash
pip install git+https://github.com/evpv-simulator/evpv.git
```

---

## ▶️ How to Run EVPV-simulator

### 🔹 Step 1: Prepare Your Config File
- Copy and adapt the [Addis Ababa example](https://github.com/evpv-simulator/evpv-examples)
- Make sure geospatial inputs are ready: region boundary, population raster, workplace list, POIs

### 🔹 Step 2: Run the CLI Model
```bash
evpv
```
Then enter the path to your config file when prompted.

### ⚠️ Notes:
- Use **absolute paths** or launch the terminal in the config file directory
- Recommended: Start by running the **Addis Ababa example** to familiarize yourself with outputs

---

## 🗂️ Input Requirements

- **Region boundary**: GeoJSON file from sources like [GADM](https://gadm.org)
- **Population density**: Raster from [GHS-POP](https://human-settlement.emergency.copernicus.eu)
- **Workplaces & POIs**: CSV with lat/lon and weight. Can be auto-generated via OSM script.

---

## 📤 Output Structure

| Folder               | Content Description                                           |
|---------------------|---------------------------------------------------------------|
| `Mobility/`         | Flows, distances, and interactive maps for trip modeling      |
| `ChargingDemand/`   | Charging power by hour and location with HTML maps            |
| `EVPV/`             | PV production and charging match indicators                    |

---

## 🧪 Advanced Usage

Import EVPV modules into your own scripts:
```python
from evpv.vehicle import Vehicle
from evpv.vehiclefleet import VehicleFleet
```
All classes are in the `evpv/` directory, such as `region.py`, `pvsimulator.py`, etc.

---

## ⭐ Features & Limitations

### ✅ Main Features
- Calibration-free gravity-based mobility demand model ([Lenormand et al. 2015](https://doi.org/10.1016/j.jtrangeo.2015.12.008))
- State-of-charge-based charging simulation ([Pareschi et al. 2020](https://doi.org/10.1016/j.apenergy.2020.115318))
- Smart charging ready: basic peak shaving rule available
- EV–PV synergy KPIs: self-consumption & self-sufficiency

### ❌ Limitations
- Weekdays only (no weekend behavior modeled)
- No intermediate stops or multi-purpose trips
- Limited validation below 5 km² traffic zone resolution
- PVGIS and OpenRouteService APIs require internet access
- Assumes closed energy system (PV only powers EVs)

---

## 📄 Scientific Publication

📘 Dumoulin et al. (2025). *A modeling framework to support the electrification of private transport in African cities: A case study of Addis Ababa*. African Transportation Research, 100064. [Link](https://www.sciencedirect.com/science/article/pii/S2950196225000420)

---
## 🎥 Step-by-step Video Support

You can find all tutorials on <a href="https://www.youtube.com/playlist?list=PLHN93NPePQ1JPEb3YFsYi3TU__bb_Xcyx" target="_blank" style="text-decoration: none;">
  <img src="https://cdn.simpleicons.org/youtube/FF0000/16" alt="YouTube" height="16" style="vertical-align: text-bottom; margin-left: 4px;">
</a>

### ❓ Need Help?

Check our [Questions & Answers](docs/faq.md) page for common issues and guidance.

---

## 📜 License

Distributed under the [GNU GPLv3](https://www.gnu.org/licenses/gpl-3.0.html).
Originally developed under the lead of EPFL PV-LAB (Switzerland). Authors involved: Jérémy Dumoulin, Alejandro Peña-Bello, Noémie Jeannin, Nicolas Wyrsch.
Now under the maintenance of the [African Energy Modelling Network](https://africanenergymodellingnetwork.net/en/home).


