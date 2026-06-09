# Sistema Inteligente de Gestión de Tickets de Soporte con Agentes y RAG

## Descripción del Proyecto

Este proyecto implementa una arquitectura basada en agentes para el procesamiento inteligente de tickets de soporte al cliente utilizando técnicas modernas de Inteligencia Artificial.

El sistema utiliza:

* Transformers
* Embeddings semánticos
* Base vectorial FAISS
* Recuperación de información tipo RAG (Retrieval Augmented Generation)
* Agentes especializados

## Dataset Utilizado

Customer Support Tickets Dataset

El conjunto de datos contiene información relacionada con tickets de soporte técnico, incluyendo:

* Tipo de ticket
* Prioridad
* Estado
* Descripción
* Tiempo de resolución
* Nivel de satisfacción del cliente

## Arquitectura del Sistema

### Agente 1: Normalizador

Responsabilidades:

* Carga del dataset
* Detección de valores nulos
* Eliminación de duplicados
* Limpieza y normalización de texto

Salida:

* Dataset limpio y preparado para procesamiento

### Agente 2: Entrenador

Responsabilidades:

* Preparación del texto
* Generación de embeddings mediante Sentence Transformers
* Construcción de una base vectorial FAISS

Tecnologías utilizadas:

* Sentence Transformers
* all-MiniLM-L6-v2
* FAISS

Salida:

* Embeddings semánticos
* Índice vectorial

### Agente 3: Comunicador

Responsabilidades:

* Recuperación de información relevante
* Generación de reportes
* Presentación de resultados

## Flujo General

Dataset

↓

Agente Normalizador

↓

Dataset Limpio

↓

Agente Entrenador

↓

Embeddings

↓

Base Vectorial FAISS

↓

RAG

↓

Agente Comunicador

↓

Reporte Final

## Tecnologías Utilizadas

* Python
* Pandas
* NumPy
* Sentence Transformers
* FAISS
* Google Colab

## Ejecución

Instalar dependencias:

pip install sentence-transformers faiss-cpu pandas numpy

Ejecutar el notebook:

3agentes.ipynb

o ejecutar el script:

3agentes.py

## Autor

Elvis Riquelme
