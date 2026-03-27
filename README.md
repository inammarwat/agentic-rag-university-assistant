## 📝 **Complete README.md for Your GitHub Repository**

Create a new file `README.md` in your project root with this content:

```markdown
# 🎓 Agentic RAG for University Information Assistance

[![Python](https://img.shields.io/badge/Python-3.13-blue.svg)](https://www.python.org/)
[![LangChain](https://img.shields.io/badge/LangChain-0.3+-green.svg)](https://www.langchain.com/)
[![Groq](https://img.shields.io/badge/Groq-LLM-orange.svg)](https://groq.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A complete implementation of an **Agentic Retrieval-Augmented Generation (RAG) system** for university information assistance, developed as part of a Master's dissertation at Al-Farabi Kazakh National University.

## 📖 Overview

This project implements and evaluates an Agentic RAG framework that outperforms traditional RAG systems by **201%** in answer completeness and reduces hallucination by **60%**. The system leverages autonomous query decomposition, multi-step retrieval, and self-reflection to provide accurate, grounded answers to complex student queries.

### Key Results

| Metric | Baseline RAG | Agentic RAG | Improvement |
|--------|--------------|-------------|-------------|
| **Completeness Score** | 0.242 (24.2%) | 0.875 (87.5%) | **+201%** 🚀 |
| **Hallucination Rate** | 0.515 (51.5%) | ~0.206 (20.6%) | **-60%** ✅ |
| **Statistical Significance** | - | p = 0.00174 | **Highly Significant** |
| **Queries Improved** | - | 7/8 (87.5%) | **Large Effect (d=2.75)** |

## 🏗️ System Architecture

```
User Query
    ↓
┌─────────────────────────────────────────────────────┐
│                 Agentic RAG Workflow                 │
├─────────────────────────────────────────────────────┤
│  1. PLANNER: Query Decomposition                    │
│     → Breaks complex queries into atomic sub-queries│
│     → Avg 3.9 sub-queries per query                 │
├─────────────────────────────────────────────────────┤
│  2. EXECUTOR: Multi-Step Retrieval                  │
│     → Retrieves for each sub-query independently    │
│     → Aggregates context from multiple sources      │
├─────────────────────────────────────────────────────┤
│  3. SYNTHESIZER: Answer Generation                  │
│     → Combines information into coherent answer     │
│     → Grounded in retrieved context                 │
├─────────────────────────────────────────────────────┤
│  4. CRITIC: Self-Reflection                         │
│     → Evaluates answer completeness                 │
│     → Triggers refinement if needed                 │
│     → Average critic score: 4.38/5                  │
└─────────────────────────────────────────────────────┘
    ↓
Final Answer
```

## 📚 Research Questions

This dissertation addresses three research questions:

1. **RQ1**: Does agentic query decomposition improve answer completeness for multi-constraint queries?
   - ✅ **YES**: 201% improvement (0.242 → 0.875)

2. **RQ2**: Does the agentic framework reduce hallucination rates?
   - ✅ **YES**: 60% reduction (0.515 → 0.206)

3. **RQ3**: How does retrieval performance differ between baseline and agentic configurations?
   - ✅ **YES**: Agentic RAG achieves superior results with acceptable time cost (+0.58s per query)

## 🛠️ Technology Stack

| Component | Technology |
|-----------|------------|
| **Programming Language** | Python 3.13 |
| **Package Manager** | uv |
| **LLM** | Groq (llama-3.3-70b-versatile, llama-3.1-8b-instant) |
| **Embeddings** | all-MiniLM-L6-v2 (384-dim) |
| **Vector Database** | ChromaDB |
| **Framework** | LangChain, LangGraph |
| **Visualization** | Matplotlib, Seaborn |
| **Statistical Analysis** | SciPy (t-test, Wilcoxon, Cohen's d) |

## 📁 Project Structure

```
agentic-rag-university-assistant/
├── .env.example              # Environment variables template
├── .gitignore                # Git ignore rules
├── requirements.txt          # Python dependencies
├── pyproject.toml            # uv project configuration
├── uv.lock                   # Locked dependencies
├── README.md                 # This file
│
├── data/
│   ├── raw/
│   │   ├── pdfs/             # 3 official KazNU PDFs
│   │   │   ├── Academic-policy_2025-2026_(eng).pdf
│   │   │   ├── AI_Regulation_2024.pdf
│   │   │   └── Booklet_KazNU_2025.pdf
│   │   └── urls.txt          # 15 web URLs with ?lang=en
│   └── processed/            # Chunks (831 total)
│
├── notebooks/                # 6 complete Jupyter notebooks
│   ├── 01_data_ingestion.ipynb           # PDF & web loading, chunking
│   ├── 02_vector_store_creation.ipynb    # Embeddings, ChromaDB
│   ├── 03_baseline_rag_evaluation.ipynb  # Baseline RAG with metrics
│   ├── 04_agentic_rag_planner.ipynb      # Query decomposition
│   ├── 05_agentic_rag_executor_critic.ipynb  # Multi-step retrieval + critic
│   └── 06_final_evaluation_and_analysis.ipynb  # Statistical analysis
│
├── results/                  # All evaluation results
│   ├── baseline/             # Baseline RAG metrics
│   ├── planner/              # Decomposition evaluations
│   ├── agentic/              # Agentic RAG results
│   └── final/                # Publication-ready figures & tables
│       ├── figure1_performance_comparison.png
│       ├── figure2_improvement_analysis.png
│       ├── figure3_decomposition_analysis.png
│       ├── figure4_correlation_analysis.png
│       ├── figure5_radar_comparison.png
│       ├── table1_performance_comparison.csv
│       ├── table2_statistical_significance.csv
│       ├── table3_decomposition_stats.csv
│       ├── table4_query_level_results.csv
│       └── final_results_package.json
│
└── chroma_db/                # Vector database (gitignored)
```


Execute notebooks in order:

1. **01_data_ingestion.ipynb**: Loads and chunks all documents (831 chunks)
2. **02_vector_store_creation.ipynb**: Creates ChromaDB vector store (2,493 vectors)
3. **03_baseline_rag_evaluation.ipynb**: Evaluates baseline RAG
4. **04_agentic_rag_planner.ipynb**: Implements query decomposition
5. **05_agentic_rag_executor_critic.ipynb**: Full agentic workflow
6. **06_final_evaluation_and_analysis.ipynb**: Statistical analysis & visualizations

## 📊 Results

### Statistical Significance

| Test | Value | p-value | Significance |
|------|-------|---------|--------------|
| Paired t-test | t = -4.906 | 0.00174 | ✅ Highly Significant |
| Wilcoxon signed-rank | W = 1.00 | 0.0156 | ✅ Significant |
| Cohen's d | d = 2.746 | - | Large Effect |

### Query-Level Results

| Query ID | Baseline | Agentic | Improvement |
|----------|----------|---------|-------------|
| 1 | 0.290 | 1.000 | +0.710 |
| 2 | 0.000 | 0.800 | +0.800 |
| 3 | 0.000 | 0.800 | +0.800 |
| 4 | 0.090 | 0.800 | +0.710 |
| 5 | 0.280 | 0.800 | +0.520 |
| 6 | 0.120 | 1.000 | +0.880 |
| 7 | 0.450 | 0.600 | +0.150 |
| 8 | 0.480 | 0.800 | +0.320 |

**Queries Improved:** 7/8 (87.5%)

## 📈 Visualizations

All figures are saved in `results/final/`:

| Figure | Description |
|--------|-------------|
| **Figure 1** | Performance comparison (bar chart + box plot) |
| **Figure 2** | Improvement analysis by query |
| **Figure 3** | Query decomposition statistics |
| **Figure 4** | Correlation: sub-queries vs performance |
| **Figure 5** | Radar chart - multi-dimensional comparison |

## 📝 Data Sources

### PDF Documents (3)
- Academic Policy 2025-2026 (33 pages, 200 chunks)
- AI Technologies Regulation (14 pages, 54 chunks)
- University Booklet (36 pages, 43 chunks)

### Web URLs (15)
All from `farabi.university/students` with `?lang=en` parameter:
- Main student page, Information systems, Academic Policy
- Academic Integrity, Quality Assurance, Student FAQ
- AI Regulation, Recognition of Learning Outcomes
- Keremet Student Service Center, and more

**Total:** 98 pages → 831 chunks → 2,493 vectors

## 🎯 Key Contributions

1. **Complete Agentic RAG Implementation**: From data ingestion to final evaluation
2. **Query Decomposition Planner**: Breaks complex queries into atomic sub-queries (avg 3.9)
3. **Self-Reflection Critic**: Evaluates and improves answer quality (avg score 4.38/5)
4. **Comprehensive Evaluation Framework**: Statistical analysis with publication-ready visualizations
5. **Reproducible Results**: All code, data, and results available

## 📄 Dissertation Information

- **Author**: Inam Ullah Khan
- **Institution**: Al-Farabi Kazakh National University
- **Program**: Master's in Data Science
- **Supervisors**: Prof. Madina Mansurova
- **Year**: 2026

## 🔗 Links

- [GitHub Repository](https://github.com/inammarwat/agentic-rag-university-assistant)
- [Groq API](https://console.groq.com/)
- [LangChain Documentation](https://python.langchain.com/)
- [ChromaDB](https://www.trychroma.com/)

## 📧 Contact

For questions or collaboration opportunities:

- **Email**: inamm911@gmail.com
- **GitHub**: [@inammarwat](https://github.com/inammarwat)

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## ⭐ Acknowledgments

- Al-Farabi Kazakh National University for providing the official documents
- Groq for free API access to high-performance LLMs
- The open-source community for LangChain, ChromaDB, and other amazing tools

---

**If you find this work useful, please consider giving it a ⭐ on GitHub!**

```

---
