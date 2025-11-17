# West Ham United — Passing Network Analytics (Premier League 2015–16)

Advanced graph-based football analytics applied to West Ham United’s 2015–16 Premier League matches.

This repository contains two Jupyter notebooks:

1) **Single-Match Analysis**
2) **Full-Season Analysis**

Both notebooks use **StatsBomb Open Data**, network science, xG-chain logic, and PCA clustering to extract tactical and performance insights from match events.

---

# 1. Match Notebook  
## **West Ham United Passing Network — Match Analysis**  
### Premier League 2015–16 — 23 January 2016  
### West Ham United 2 – 2 Manchester City  
**Notebook file:** `whu_match_2016-01-23.ipynb`

### **Overview**
This notebook performs a deep tactical breakdown of one match using network theory. Key steps include:

- Loading and parsing StatsBomb event JSON  
- Filtering completed WHU passes  
- Tagging progressive passes (distance-to-goal reduction)  
- Identifying goal-chain sequences  
- Aggregating edges between players  
- Building a **spatially anchored directed passing network**  
- Computing centrality metrics:
  - Degree centrality  
  - Betweenness centrality  
  - Closeness centrality  
  - Eigenvector centrality  
- Computing **Goal-Chain Impact Score per 90** (build-up involvement + assists)

---

## **Match Visualizations**

### **Spatial Passing Network Visualization**
<img src="graph.png" width="100%">

This graphic shows:

- Players positioned at their average on-ball locations  
- Node size scaled by **eigenvector centrality** (quality of connections)  
- Edge width scaled by a **composite passing impact weight**:
  - total passes  
  - progressive passes  
  - assists  
  - goal-chain actions  
- Arrows showing direction & frequency of connections  

This combines tactical structure + network influence in one view.

---

### **Goal-Chain Impact Scoring**
<img src="goal_chain.png" width="100%">

This visualization shows which WHU players contributed most to:

- build-up passes in goal-scoring possessions  
- passes received in those same possessions  
- assists  
- per-90 adjusted impact score  

It highlights which players were central to the scoring process — beyond just goals and assists.

---

---

# 2. Full Season Notebook  
## **West Ham United Passing Network — Full-Season Analysis (2015–16)**  
### Advanced Influence Metrics, Progression Analysis & PCA Role Clustering  
**Notebook file:** `whu_full_season_passing_networks.ipynb`

### **Helicopter View — What This Notebook Does**
This full-season pipeline processes **38 Premier League matches** and aggregates passing networks across the season to study:

- Individual player influence  
- Structural importance in possession  
- Progression profiles  
- Goal-chain behavior  
- xG-chain contribution  
- Role-based clustering

Key techniques used:

- Directed weighted network graphs per match  
- Progressive pass detection  
- Goal-chain + xG-chain derived metrics  
- Eigenvector / betweenness / closeness / centrality  
- Time series analysis  
- PCA dimensionality reduction  
- KMeans role clustering (FB, CM, WF, CF)

---

## **Season-Level Outputs**

### **Season Summary Table for top 15 WHU players**
<img src="top_15_players.png" width="100%">

---

### **Top 3 Players — Time Series Progression**

For **Dimitri Payet**, **Mark Noble**, and **Aaron Cresswell**, we plot two timelines:

1) **Network Influence**  
   - degree centrality  
   - betweenness  
   - closeness  
   - eigenvector  

2) **On-Ball Impact**  
   - progressive passes  
   - pressurized passes  
   - assists  
   - xG-chain  

#### **Dimitri Payet Time Series Progression**

<img src="Dmitri_Payet.png" width="100%">

#### **Mark Noble Time Series Progression**

<img src="Mark_Noble.png" width="100%">

#### **Aaron Cresswell Time Series Progression**

<img src="Aaron_Cresswell.png" width="100%">

---

### **Dimensionality Reduction & Role-Based Clustering**

Using PCA(3) + KMeans(4), players are clustered into 4 intuitive tactical roles:

- **FB** — Fullbacks (wide, medium progression)  
- **CM** — Central midfielders (high involvement, high pass volume)  
- **WF** — Wingers / creators (progressive actions, xG-chain)  
- **CF** — Forwards (goal-chain, low network centrality but high xG involvement)

This provides a data-driven lens on squad roles.

<img src="3D_PCA.png" width="100%">


---

# Summary

This repository provides a complete analysis framework for:

- match-level tactical insights  
- season-level influence profiling  
- player role discovery  
- progression + goal involvement modeling  
- interactive visual outputs suitable for scouting, research, and coaching conversations  

It combines football knowledge with modern data science methods to uncover patterns in team structure, player development, and tactical identity.

---

# Citation

Raw match data comes from:  
**StatsBomb Open Data**  
https://github.com/statsbomb/open-data  
