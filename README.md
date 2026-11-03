# SI3003 — Proyecto Final: NeuroPattern Agent

## Información General
- **Integrantes:** Alejandro Lotero Valencia
- **Curso:** Inteligencia Artificial (SI3003)
- **Alternativa elegida:** Opción B — Agente con herramientas

---

## 1. Definición del Problema

### ¿Qué problema queremos resolver y para quién?
El análisis exploratorio de registros de actividad neuronal (series temporales de picos o características espectrales) suele requerir la ejecución de scripts manuales y análisis estadísticos repetitivos. Desarrollaremos un prototipo de agente inteligente orientado a estudiantes e investigadores de neurociencia que permita realizar consultas conversacionales sobre datos de actividad neuronal, automatizando la detección de patrones anómalos.

### ¿Qué preguntas o tareas atenderá el prototipo?
El agente podrá responder a solicitudes como:
- *"Realiza una revisión general del Paciente 1."*
- *"¿Se detectan picos de disparo o anomalías en la señal del Paciente 2?"*
- *"Analiza el archivo CSV cargado y determina si su tasa de disparo supera los umbrales normales."*

### ¿Por qué elegimos la Opción B (Agente con herramientas)?
La arquitectura de agente permite integrar la capacidad conversacional y la flexibilidad de un modelo de lenguaje (LLM) con funciones deterministas en Python (usando NumPy y Scikit-learn). De esta manera, el modelo no alucina ni calcula métricas complejas directamente, sino que decide cuándo invocar herramientas numéricas exactas para procesar los patrones neuronales.

### Alcance y Limitaciones
**Fuera del alcance:**
- Entrenamiento de redes neuronales desde cero o modelos de Deep Learning pesados.
- Procesamiento de archivos de neuroimagen crudos (como fMRI o EEG multicanal en formatos complejos tipo BDF/EDF).
- Validación de formatos CSV arbitrarios que no cumplan con el esquema predefinido del sistema.

---

## 2. Datos y Herramientas

### Origen de los datos
Se utilizarán conjuntos de datos sintéticos estructurados en formato CSV que simulan series temporales de tasa de disparo neuronal y métricas de amplitud espectral. Los archivos de prueba estarán disponibles en la carpeta `data/` de este repositorio.

### Herramientas definidas para el Agente
1. `analizar_patron_neuronal`: Recibe el identificador de un paciente o la ruta a un archivo CSV. Calcula métricas de dispersión, desviaciones estándar y ejecuta un algoritmo de detección de anomalías (como *Isolation Forest* o umbrales estadísticos) para identificar picos de actividad anormales.
2. `consultar_base_clinica_neuro`: Cruza los hallazgos cuantitativos devueltos por la primera herramienta con una base de conocimiento teórica/clínica para contextualizar el tipo de patrón detectado.
