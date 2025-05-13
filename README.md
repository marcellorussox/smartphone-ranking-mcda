```markdown
# Smartphone Ranking with ELECTRE-III 🚀

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green)](https://opensource.org/licenses/MIT)

A Multi-Criteria Decision Analysis (MCDA) project to rank premium smartphones based on technical specifications, **excluding price**. Built with Python, Jupyter Notebook, and the ELECTRE-III method.

---

## 📋 Project Overview

**Goal**: Rank premium smartphones using non-monetary criteria (e.g., battery life, camera quality) to assist tech-savvy users in making informed decisions.  

**Method**:  
- **ELECTRE-III** for outranking-based ranking.  
- **3 configurations** to test different user priorities (balanced, performance-focused, durability-focused).  

**Criteria**:  
- **Maximize**: Battery Capacity, Camera Resolution, Processor Performance, Storage, Water Resistance.  
- **Minimize**: Weight.  

---

## 🗂 Repository Structure

```
smartphone-ranking-mcda/
├── data/                   # Raw and processed data
│   ├── smartphones_raw.csv
│   └── performance_matrix.csv
├── configs/                # ELECTRE-III parameter configurations
│   ├── balanced.yaml
│   ├── performance.yaml
│   └── durability.yaml
├── notebooks/              # Jupyter Notebook for analysis
│   └── analysis.ipynb
├── results/                # Results for each configuration
│   ├── balanced/
│   │   ├── rankings.csv
│   │   └── credibility_matrix.csv
│   ├── performance/
│   └── durability/
├── docs/                   # Documentation
│   ├── report.md
│   └── methodology.md
└── README.md

---

## 🛠 Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/smartphone-ranking-mcda
   cd smartphone-ranking-mcda
   ```

2. **Install dependencies**:
   ```bash
   pip install pandas matplotlib jupyter pyyaml
   ```

---

## 🚀 Usage

### Step 1: Data Collection
- Populate `data/smartphones_raw.csv` with real data from sources like [GSMArena](https://www.gsmarena.com/) or [AnTuTu](https://www.antutu.com/).  
- Format example:
  | Smartphone          | Battery (mAh) | Camera (MP) | Processor (AnTuTu) | Water Resistance | Storage (GB) | Weight (g) |
  |---------------------|---------------|-------------|---------------------|------------------|--------------|------------|
  | iPhone 15 Pro Max   | 4500          | 48          | 1,450,000          | 3                | 512          | 240        |

### Step 2: Configure Parameters
Edit YAML files in `configs/` to define weights, thresholds, and veto values.  

### Step 3: Run Analysis
1. Start Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
2. Open `notebooks/analysis.ipynb` and execute cells to:  
   - Load data and configurations.  
   - Run ELECTRE-III for each configuration.  
   - Generate rankings and visualizations.  

### Step 4: Explore Results
- Rankings and credibility matrices are saved in `results/<config_name>/`.  
- Use the notebook to create plots (bar charts, heatmaps, radar plots).  

---

## ⚙️ Example Configuration

`configs/balanced.yaml`:
```yaml
criteria:
  battery:
    weight: 0.18
    q: 100      # Indifference threshold (mAh)
    p: 500      # Preference threshold (mAh)
    v: 2000     # Veto threshold (mAh)
    direction: max
  camera:
    weight: 0.16
    q: 10       # Indifference threshold (MP)
    p: 30       # Preference threshold (MP)
    v: 12       # Veto threshold (MP)
    direction: max
  # ... (similar for other criteria)
```

---

## 📊 Sample Results

![Rankings Preview](docs/images/rankings_preview.png) *Example rankings for balanced configuration.*

---

## 🤝 Contributing

Contributions are welcome!  
1. Fork the repository.  
2. Create a feature branch: `git checkout -b feature/new-analysis`.  
3. Commit changes: `git commit -m 'Add new feature'`.  
4. Push to the branch: `git push origin feature/new-analysis`.  
5. Open a Pull Request.

---

## 📜 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

**Made by [Marcello Russo]**  
*For questions or feedback, open an issue or contact [m.russo@mareasoftware.com].*


---

### 🔥 Highlights  
- **Clear Structure**: Easily navigable folders and documentation.  
- **Reproducibility**: All data and configurations are transparent.  
- **Visual Appeal**: Badges, tables, and emojis to enhance readability.  
- **Jupyter Integration**: Interactive analysis with minimal setup.