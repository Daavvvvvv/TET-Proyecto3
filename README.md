# TÓPICOS TELEMÁTICA - ST0263

## Estudiantes: 
- Antonio Carbonó Pedroza, hacarbonop@eafit.edu.co
- David Elias Franco Vélez, defrancov@eafit.edu.co
- Daniel Vélez Duque, dvelezd2@eafit.edu.co  
- Juan José Villada Calle, jjvilladac@eafit.edu.co

## Profesor: 
- Alvaro Enrique Ospina Sanjuan, aeospinas@eafit.edu.co

## 1. Descripción
Este proyecto aborda la automatización del ciclo completo de Captura, Ingesta, Procesamiento y Salida de datos para la gestión de datos relacionados con COVID-19 en Colombia, utilizando una arquitectura *Batch* para Big Data. La solución se basa en la integración de fuentes de datos proporcionadas por el Ministerio de Salud, accesibles a través de APIs y archivos CSV, junto con datos simulados almacenados en una base de datos relacional (`SQLite`).

### 1.1. Aspectos Cumplidos (Requerimientos Funcionales y No Funcionales)
- **Captura de Datos desde APIs y CSV**: El acceso a datos abiertos del `Ministerio de Salud` es automatico.
- **Ingesta de Datos**: La descarga de datos y su transformación inicial se emplea usando `Spark` y una base de datos `SQLite`.
- **Procesamiento y Análisis de los Datos:** Se unen, limpian, contrastan y procesan los datos provenientes de múltiples fuentes.

### 1.2. Aspectos No Cumplidos
- **Implementación de Modelos de Aprendizaje Automático**: Aunque opcional, no se implementó un modelo supervisado/no supervisado con `SparkML`.
  
## 2. Arquitectura
1. **Fuentes de Datos**:
   - API del Ministerio de Salud (`JSON`).
   - Base de datos relacional simulada (`SQLite`).
2. **Zona RAW (AWS S3)**:
   - Almacenamiento inicial de datos sin procesar.
3. **Procesamiento (AWS EMR)**:
   - Clúster con Spark para ejecutar `pipelines ETL`.
4. **Zona Trusted y Refined (AWS S3)**:
   - Almacenamiento de datos procesados y resultados analíticos.
5. **Consulta de Resultados**:
   - `Amazon Athena` para consultas SQL.
   - `API Gateway` para acceso programático.

## 3. Tecnologías Utilizadas:
- `Python` (3.9+)
- `Pandas` (1.5.0)
- `Apache Spark` (3.3.1)
- `SQLite`
  
## 4. Guía de Uso
Para replicar el proyecto, ejecutar el programa `Proyecto3_TET.ipynb` en Google Colab.

### 4.1 Imágenes del Proyecto

![2](https://github.com/user-attachments/assets/2eca4b28-f3f1-46dc-8443-7df7599b2257)

![1](https://github.com/user-attachments/assets/780c5443-1c37-4e5c-b875-052fc44726c8)

### 4.4 [Video](https://youtu.be/XEMvexeCWng)
 
## 5. Referencias:
- Google LLC. (2024). Google Colab Documentation. Recuperado de [https://colab.research.google.com/](https://colab.research.google.com/)
- Apache Software Foundation. (2024). Apache Spark Documentation. Recuperado de [https://spark.apache.org/docs/latest/](https://spark.apache.org/docs/latest/)
- Amazon Web Services, Inc. (2024). AWS Big Data Services Documentation. Recuperado de [https://docs.aws.amazon.com/](https://docs.aws.amazon.com/)
