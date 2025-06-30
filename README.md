# 🔬 BioGraphIQ – Graph AI for Biomedical Discovery

**BioGraphIQ** is a Graph AI + Cheminformatics project designed to model and explore complex relationships among drugs, diseases, and pathogens using Neo4j, Elasticsearch, and semantic web technologies. This project fuses knowledge graphs with high-performance search to enable biomedical insights and intelligent querying at scale.

---

## 🧬 Overview

Biomedical data is inherently networked—drugs affect diseases, pathogens cause illnesses, and all entities are linked in intricate, evolving ways. **BioGraphIQ** leverages graph-based models and semantic search to:

- Represent complex biomedical interactions with knowledge graphs
- Enable intuitive exploration of biological knowledge
- Deliver fast, fuzzy, and full-text queries for drug discovery and disease analysis

This project sits at the intersection of **cheminformatics**, **biomedical informatics**, and **graph data science**.

---

## 🛠️ Tech Stack

| Tool/Library         | Purpose                                                               |
|----------------------|-----------------------------------------------------------------------|
| **Neo4j**            | Graph database for modeling biomedical entities                       |
| **Cypher**           | Query language for graph traversal and analysis                       |
| **Neo4j GDS**        | Graph Data Science (e.g., PageRank, centrality, community detection)  |
| **NeoSemantics (n10s)** | RDF/OWL support and ontology integration                          |
| **Wikidata SPARQL**  | Ontology querying and enrichment                                      |
| **Apache Lucene**    | Built-in text indexing in Neo4j for full-text search                  |
| **Elasticsearch**    | External semantic + fuzzy search engine for biomedical records        |
| **KEGG API**         | Data source for genes, drugs, diseases, and interactions              |

---

## 📁 Dataset

Sourced from **KEGG (Kyoto Encyclopedia of Genes and Genomes)** using API access. Structured in a relational format before graph transformation:

- `Drug.csv`
- `Disease.csv`
- `Pathogen.csv`
- `Drug-Disease.csv`
- `Pathogen-Disease.csv`

---

## 🧩 Project Modules

### 1. 🔗 Knowledge Graph Construction
- Used **Neo4j** to visualize and connect entities (e.g., drugs, diseases, pathogens)
- Queried node-degree, shortest paths, disease clusters
- Applied **PageRank** to detect high-impact biomedical entities

### 2. 🔍 Full-Text & Fuzzy Search (Lucene-based)
- Implemented search over drug/disease descriptions in Neo4j
- Used **Apache Lucene** under-the-hood (via Cypher procedures)
- Supported wildcard (`*`, `?`) and fuzzy (`~`) biomedical queries

### 3. 🌐 Semantic Ontology Enrichment
- Queried **Wikidata SPARQL** for RDF triples (e.g., subclass of "Infectious Disease")
- Imported ontologies using **Neosemantics (n10s)** into Neo4j
- Constructed **OWL-based knowledge graphs** with biomedical hierarchy

### 4. ⚡ Elasticsearch-Enhanced Search *(New!)*
To scale search beyond Neo4j's internal Lucene:

- Indexed all biomedical entities in **Elasticsearch**
- Added **custom analyzers** for stopwords, stemming, synonyms
- Implemented **DSL queries** to search across drug effects, disease classes, and drug-disease matches
- Enabled **fuzzy, phrase, and nested queries** over large biomedical corpora

Example:
```json
{
  "query": {
    "match": {
      "description": {
        "query": "antibiotic malaria",
        "fuzziness": "AUTO"
      }
    }
  }
}
```

---

## 🔬 Sample Use Cases

* Find all drugs used to treat a specific class of diseases (e.g., "Infectious Diseases")
* Search for "antibiotic" drugs with fuzzy or partial terms using Elasticsearch
* Discover hidden pathogen clusters using community detection
* Enrich graph with new disease subclasses in real-time from Wikidata

---

## 🌟 Highlights

* 🌐 **Graph-based biomedical modeling** with Neo4j
* 📚 **Ontology-powered knowledge graphs** using RDF and SPARQL
* 🔍 **Dual-layer semantic search** via Lucene and Elasticsearch
* 📈 **Graph analytics** using GDS (e.g., PageRank for disease impact)
* 🚀 **Production-ready** knowledge infrastructure for real-world biomedical discovery

---

## 🧠 Future Enhancements

* Integrate **GraphQL API** for query + CRUD access
* Apply **Graph Neural Networks (GNNs)** for link prediction and node classification
* Build a biomedical **search dashboard** using Streamlit or React
* Explore drug repurposing with **knowledge graph embeddings**

---

## 👩‍💻 Author

**Harshini K. Aiyyer**  
*Data & AI Enthusiast | Biomedical + Graph Data Science*  
📫 [harshini.k.aiyyer@gmail.com](mailto:harshini.k.aiyyer@gmail.com)  
🔗 [LinkedIn](https://linkedin.com/in/harshini-aiyyer) · [GitHub](https://github.com/HarshiniAiyyer)

---

## 📚 References

* KEGG – [https://www.kegg.jp/](https://www.kegg.jp/)
* Neo4j – [https://neo4j.com/](https://neo4j.com/)
* Wikidata SPARQL – [https://query.wikidata.org/](https://query.wikidata.org/)
* Elasticsearch – [https://www.elastic.co/elasticsearch](https://www.elastic.co/elasticsearch)
