# rag_wikipedia-lab
# Task 2 — Wikipedia-based RAG Summarizer  
**Proyecto para el curso de Data Science – RAG con LangChain + ChromaDB**

Este repositorio implementa un sistema de **summarization RAG (Retrieval-Augmented Generation)** utilizando datos de Wikipedia, embeddings con SentenceTransformers y un vector store persistente en ChromaDB. Todo el desarrollo está hecho con **Python**, **LangChain**, **Chroma**, **SentenceTransformers** y **HuggingFace**.  

El objetivo es construir un pipeline capaz de:
1. Extraer datos reales desde Wikipedia  
2. Procesarlos y chunkearlos  
3. Generar embeddings  
4. Almacenar los vectores en ChromaDB  
5. Consultarlos mediante un sistema de recuperación  
6. Generar un resumen final basado en las partes más relevantes  

---

## Estructura del Repositorio
rag_wikipedia-lab/
│
├── data/
│ ├── wiki_corpus.csv # Dataset extraído y procesado desde Wikipedia
│ └── chroma_store.zip # Vector store persistente utilizado para el RAG
│
├── notebooks/
│ └── rag_wikipedia.ipynb # Notebook con todo el pipeline RAG implementado
│
├── outputs/
│ ├── rag_summary.md # Resumen final de 400–500 palabras
│ └── retrieval_examples.json # Ejemplos de consultas y respuestas
│
└── README.md # Documentación del proyectorag_wikipedia-lab/
│
├── data/
│ ├── wiki_corpus.csv # Dataset extraído y procesado desde Wikipedia
│ └── chroma_store.zip # Vector store persistente utilizado para el RAG
│
├── notebooks/
│ └── rag_wikipedia.ipynb # Notebook con todo el pipeline RAG implementado
│
├── outputs/
│ ├── rag_summary.md # Resumen final de 400–500 palabras
│ └── retrieval_examples.json # Ejemplos de consultas y respuestas
│
└── README.md # Documentación del proyecto


---

## Tecnologías utilizadas

- **Python 3.10+**
- **LangChain** (retrieval + chain pipeline)
- **ChromaDB** (almacenamiento vectorial)
- **SentenceTransformers** — `all-MiniLM-L6-v2`
- **wikipedia-api**
- **transformers** + **HuggingFacePipeline**
- **pandas**, **numpy**, **markdown**
- **Google Colab** como entorno de ejecución

---

## Descripción del Pipeline

###  Extracción de datos (Wikipedia)
Se utiliza `wikipedia-api` para obtener el contenido del artículo:



El texto se limpia y se divide en chunks de ~300 palabras.

---

### Creación del dataset
Los chunks se guardan en:
data/wiki_corpus.csv

con columnas:

- `id`
- `title`
- `text`

---

###  Embeddings + Vector Store
- Se usa el modelo `all-MiniLM-L6-v2`
- Embeddings generados con SentenceTransformers
- Los vectores se almacenan en una colección llamada:

wiki_ai

Luego se exporta un vector store persistente:

data/chroma_store.zip


---

### Retrieval Pipeline (LangChain)
El sistema de recuperación utiliza:

- `Chroma` como vector store
- `HuggingFacePipeline` como LLM local
- Un chain estilo `stuff` para juntar los documentos recuperados

Consultas de ejemplo están en:

outputs/retrieval_examples.json

---

###  Generación del resumen final
Usando los vectores recuperados, se arma un resumen coherente de **400–500 palabras**, guardado en:
 outputs/rag_summary.md

 
---

##  Trabajo Colaborativo

El proyecto fue desarrollado en parejas.  
Las contribuciones están claramente divididas mediante **Pull Requests**:

###  PR – Valeria:
- Extracción y procesamiento de datos
- Creación del dataset
- Creación del vector store persistente  
- Organización inicial del repo

###  PR – Sebastián:
- Construcción del retrieval pipeline
- Implementación del RAG con LangChain
- Generación del resumen final
- Creación de retrieval_examples.json

Ambos Pull Requests están aprobados y mergeados a `main`.

---

##  Entregables oficiales

- `/notebooks/rag_wikipedia.ipynb`  
- `/data/wiki_corpus.csv`  
- `/data/chroma_store.zip`  
- `/outputs/rag_summary.md`  
- `/outputs/retrieval_examples.json`

---

##  Cómo ejecutar

1. Clonar el repo  
2. Descomprimir `data/chroma_store.zip` dentro de `data/` (si se desea regenerar la colección)  
3. Abrir el notebook en Google Colab  
4. Instalar dependencias  
5. Ejecutar todas las celdas

---

##  Autores

- **Valeria Lovatón** – Data processing & embeddings  
- **Sebastián Pizarro** – Retrieval pipeline & summarized output  

Universidad del Pacífico — 2025  
Proyecto para el curso de Data Science

---









