# HYBRID MOVIE RECOMMENDER

Este proyecto implementa un sistema de recomendación de películas usando un enfoque híbrido:
- Similitud semántica (NLP) sobre información de contenido (géneros, keywords, reparto y director).
- Similitud numérica sobre metadatos (valoración, duración y fecha de estreno).

El resultado es un recomendador content-based enriquecido con señales “objetivas” para mejorar la calidad y coherencia de las recomendaciones.

📌 Objetivo

Dada una película, el sistema devuelve un Top-5 de películas similares basándose en:
-Contenido y personas (cast + director + géneros + palabras clave).
-Metadatos (puntuación media, duración, recencia).

🧰 Tecnologías y librerías
- Python
- NumPy y Pandas para manipulación de datos
- Scikit-learn
- TfidfVectorizer (representación vectorial de texto)
- cosine_similarity (medida de similitud)
- MinMaxScaler (normalización de variables numéricas)
- JSON parsing para transformar columnas almacenadas como strings JSON

📂 Dataset y preparación

Se cargan dos ficheros CSV (créditos y películas) y se integran mediante merge por el título:
- tmdb_5000_movies.csv
- tmdb_5000_credits.csv

Limpieza y selección de variables

Se seleccionan columnas relevantes a partir del estudio de las mismas:

genres, keywords, cast, crew, release_date, runtime, vote_average, vote_count, etc.

Se eliminan filas con valores nulos en campos críticos (dropna).
