# **📺 Caso Netflix**

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/7a/Logonetflix.png/800px-Logonetflix.png" width=400px/>

***Netflix*** es un servicio de transmisión over-the-top de video bajo demanda por suscripción estadounidense. El servicio distribuye principalmente películas y programas de televisión originales y adquiridos de varios géneros y está disponible internacionalmente en varios idiomas.

# **💬 Opinión de Usuarios de Netflix**

***Netflix Inc.*** se encuentra interesado en conocer bien qué opinan sus usuarios y el público en general sobre su servicio *(Niveles de Servicio al Cliente)*. Se plantea que al conocer las opiniones que rondan en el internet podrán identificar en lo que pueden mejorar su servicio.

La empresa se encuentra interesada en conocer lo que opinan en internet sobre su servicio y analizar qué es lo que más se habla sobre sus servicio; lo bueno y lo malo.

# **📋 Proceso de Minería de Datos (CRISP DM)**

El proceso de Minería de Datos en este escenario, siguiendo el modelo ***CRISP-DM***, se puede describir de la siguiente manera:

### Etapa de Entendimiento del Negocio:

1. **Objetivos del Negocio**: Mejorar su servicio al cliente mediante la comprensión de las opiniones de los usuarios a través de las reseñas en TrustPilot.com.

### Etapa de Entendimiento de los Datos:

2. **Obtención de Datos**: Utilizar técnicas de Web Scraping para recolectar miles de reseñas sobre el servicio de Netflix junto con su calificación de 1 a 5 estrellas desde TrustPilot.com. Almacenar estos datos en un archivo CSV con las columnas "review" y "score".

3. **Exploración de Datos**: Realizar un análisis exploratorio de los datos para comprender su estructura y características. Esto incluye la revisión de estadísticas descriptivas, como la distribución de las calificaciones y la longitud de las reseñas.

### Etapa de Preparación de Datos:

4. **Preparación de Datos**: Aplicar técnicas de procesamiento de lenguaje natural (NLP) utilizando SPACY en Python para limpiar las reseñas. Esto incluye la eliminación de símbolos de puntuación, caracteres especiales, lematización, stemming y eliminación de stopwords. Guardar los textos procesados en otro archivo CSV.

### Etapa de Modelado:

5. **Filtrado de Reseñas Negativas**: Filtrar las reseñas que tienen una calificación menor de 3 estrellas, ya que estas se consideran negativas. Estas reseñas se utilizarán para el análisis de palabras clave.

6. **Análisis de Palabras Clave en Reseñas Negativas**: Aplicar técnicas de procesamiento de texto para identificar las palabras más frecuentes en las reseñas negativas. Esto puede incluir la creación de un gráfico de palabras clave con letras de diferente tamaño para visualizar las palabras más mencionadas.

7. **Análisis de Palabras Clave en Reseñas Positivas**: Realizar el mismo análisis de palabras clave en las reseñas con una calificación de 3 estrellas o superior. Esto ayudará a comprender las opiniones positivas de los usuarios.

### Etapa de Evaluación:

8. **Selección de Modelos de Machine Learning**: En esta etapa, se debe determinar qué tipo de modelo de Machine Learning es más adecuado para el análisis. Dado que se planea implementar una regresión logística para predecir la puntuación de una reseña basada en su contenido, se ha elegido este modelo debido a su capacidad para trabajar con características de texto. Además, el uso de TfidfVectorizer permitirá ponderar el impacto de cada palabra en la reseña en el modelo.

### Etapa de Modelado:

9. **Preparación de Datos para el Modelo de Regresión Logística**: Los datos limpios y preprocesados, junto con las puntuaciones, se utilizarán para entrenar el modelo de regresión logística. Antes de hacerlo, se aplicará TfidfVectorizer para transformar las palabras en características numéricas y ponderar su importancia en las reseñas.

10. **Entrenamiento del Modelo de Regresión Logística**: Utilizar los datos preparados para entrenar el modelo de regresión logística. El objetivo es que el modelo aprenda a predecir la puntuación de una reseña basándose en el contenido textual de la misma.

### Etapa de Evaluación:

11. **Evaluación del Modelo de Regresión Logística**: Evaluar el rendimiento del modelo utilizando métricas de regresión, como el error cuadrático medio (MSE) o el coeficiente de determinación (R2). Esto permitirá comprender qué tan bien el modelo es capaz de predecir la puntuación de una reseña en función de su contenido textual.

### Etapa de Implementación:

12. **Implementación del Modelo de Regresión Logística**: Integrar el modelo de regresión logística en los procesos de análisis de opiniones de los usuarios en tiempo real. Esto podría implicar la clasificación automática de nuevas reseñas a medida que llegan a la plataforma de Netflix para ayudar a comprender el sentimiento de los usuarios y la posible puntuación asociada a sus opiniones. Además, se deja la posibilidad de analizar comentarios de redes sociales como Twitter y Facebook, el modelo de regresión logística podría ser aplicado para evaluar el sentimiento de las personas en estas plataformas, lo que podría ser valioso para comprender la percepción pública y la satisfacción del cliente en tiempo real.