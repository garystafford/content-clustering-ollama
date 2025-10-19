# Content Segmentation and Labeling with PCA, K-Means, Generative AI

This notebook demonstrates an approach to video content recommendations using machine learning and Generative AI. By analyzing semantic relationships rather than just metadata tags, this technique offers an effective solution for content recommendation.

## Key Features

- **Data Analysis:** Examines metadata from 150 recent movies, shows, and series to identify content similarities and relationships
- **Semantic Vectorization:** Transforms content's metadata into dense vector embeddings using a text embedding model
- **Dimensional Analysis:** Employs Principal Component Analysis (PCA) for dimensionality reduction and K-Means for cluster identification
- **Visual Representation:** Creates interactive 2D scatter plots to visualize content relationships and clustering patterns
- **AI-Powered Insights:** Leverages Generative AI to produce natural language descriptions of each content cluster and extract meaningful keywords

This approach enables content platforms to automatically group similar videos based on deep semantic connections rather than superficial categorization, significantly enhancing recommendation accuracy and content discovery.

## Workflow Diagram

```mermaid
flowchart TD
    A["Load Content Metadata"] --> B["Prepare Metadata
    for Embedding"]
    B --> C["Generate Embeddings"]
    C --> E["Perform Dimensionality
    Reduction"]
    E --> H["Determine Optimal
    Cluster Count"]
    H --> L["Apply K-Means
    Clustering"]
    L --> M["Access Cluster Labels
    and Centroids"]
    M --> N["Store Cluster Associations
    and Embeddings"]
    N --> S["Generate Descriptions
    for Clusters"]
    N --> T["Generate Keywords
    for Clusters"]
    S --> V[Store Cluster Descriptions
    and Keywords]
    T --> V
```

**Workflow Steps:**

1. **Data Loading**: Load content metadata (150 items)
2. **Text Preparation**: Combine genres, keywords, and descriptions
3. **Embedding Generation**: Create semantic vectors using embedding model
4. **Dimensionality Reduction**: Reduce to 2D using PCA or t-SNE
5. **Cluster Optimization**: Find optimal K using elbow method
6. **Clustering**: Apply K-Means to group similar content
7. **Visualization**: Create pie charts and scatter plots
8. **AI Interpretation**: Generate descriptions and keywords using LLM
9. **Export Results**: Save enhanced data with cluster assignments

## Installation for Ollama

```bash
ollama pull qwen3-embedding:4b
ollama pull gpt-oss:20b
```

```bash
python -m pip install virtualenv --break-system-packages -Uq
python -m venv .venv
source .venv/bin/activate

python -m pip install pip -Uq
python -m pip install -r requirements_ollama.txt -Uq
```

## Installation for Amazon Bedrock

```bash
python -m pip install virtualenv --break-system-packages -Uq
python -m venv .venv
source .venv/bin/activate

python -m pip install pip -Uq
python -m pip install -r requirements_bedrock.txt -Uq
```
