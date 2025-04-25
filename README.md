# 🌾 Crop Recommender System with Knowledge Graphs

*An intelligent system that combines agronomic knowledge graphs with machine learning for optimal crop selection*

![Python](https://img.shields.io/badge/Python-3.8+-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Neo4j](https://img.shields.io/badge/Neo4j-4.0+-green)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0+-yellow)

## 📌 Overview
This system recommends crops based on:
- **Soil properties** (pH, NPK levels)
- **Climate conditions** (rainfall, temperature)
- **Geospatial data**
- **Farm historical data**
- **Market trends**

## 🌟 Key Features
- **Knowledge Graph Integration**: Structured agricultural knowledge using RDF/OWL
- **Rule-based Reasoning**: Implements FAIR agricultural principles
- **Context-Aware Recommendations**: Regional adaptation for 50+ crops
- **Explainable AI**: Clear justification for recommendations

## 🧠 Architecture

graph TD
    A[Soil Data] --> C[Knowledge Graph]
    B[Weather Data] --> C
    C --> D[Graph Embeddings]
    D --> E[Recommendation Engine]
    E --> F[Farmer Interface]

🚀 Quick Start
**Prerequisites**
- Neo4j Desktop (v4.4+)
- Python 3.8+
- Agricultural datasets (sample provided)

**Installation**
git clone https://github.com/Osowomuabe/Crop_Recommender_System_using_Knowledge_Graphs.git
cd Crop_Recommender_System_using_Knowledge_Graphs

# Install dependencies
pip install -r requirements.txt

# Start Neo4j database (configure in config/neo4j.yaml)
neo4j start

**Running the System**
from recommender import CropAdvisor

advisor = CropAdvisor()
recommendations = advisor.query(
    location="7.0,4.5",  # Lat/Long
    soil_type="loamy",
    rainfall=1200  # mm/year
)

📂 Project Structure
├── CROP_RECOMMENDER_SYSTEM_USING_KNOWLEDGE_GRAPHS.ipynb  # Demo notebook
├── crop_recommender_system_using_knowledge_graphs.py     # Core module
├── knowledge_graph/
│   ├── agri_schema.owl    # Ontology definition
│   └── neo4j_loader.py    # Data ingestion
├── data/
│   ├── soil_samples.csv
│   └── crop_properties.ttl
└── config/
    ├── neo4j.yaml         # Database config
    └── constraints.rq     # SPARQL rules

📊 Example Output

{
  "recommended_crops": [
    {
      "crop": "Cassava",
      "confidence": 0.92,
      "reasoning": "Matches soil pH (5.5-6.5) and annual rainfall (1000-1500mm)"
    },
    {
      "crop": "Yam",
      "confidence": 0.87,
      "reasoning": "Thrives in loamy soils with good drainage"
    }
  ]
}

📚 References
- AGROVOC Knowledge Graph (FAO)
- Crop suitability models (FAO EcoCrop)
- Semantic Web technologies (W3C)

  
