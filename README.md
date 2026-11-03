# EEG-Agent: Análisis Espectral y Educativo de Bandas EEG

**Asignatura:** SI3003 — Inteligencia Artificial  
**Estudiante:** Alejandro Lotero Valencia  
**Alternativa seleccionada:** Opción B — Agente con herramientas  

---

## 1. Descripción del Problema
El electroencefalograma (EEG) registra la actividad eléctrica cerebral a través de oscilaciones agrupadas en bandas de frecuencia (**Delta, Theta, Alpha y Beta**). Para los estudiantes, identificar estas bandas, calcular su potencia y relacionarlas con la neurofisiología suele ser complejo. Este proyecto implementa un agente inteligente que automatiza este análisis mediante herramientas de procesamiento de señales y consulta teórica.

**No realiza diagnósticos clínicos ni interpretaciones médicas individuales.**

---

## 2. Arquitectura y Herramientas del Agente
El LLM decide dinámicamente el uso de tres herramientas implementadas en Python (máximo 3 llamadas por consulta):

1. `analizar_senal_eeg()`: Valida los datos, calcula el espectro mediante FFT/Welch y estima la potencia relativa de las cuatro bandas.
2. `consultar_conceptos_eeg()`: Consulta una base de conocimiento local en formato JSON sobre ritmos cerebrales, artefactos y fundamentos neurofisiológicos.
3. `comparar_bandas()`: Evalúa las potencias relativas, identifica la banda predominante y organiza las diferencias porcentuales.

---

## 3. Fuentes de Datos
* Se emplearán registros normalizados de EEG (en formato compatible con Pandas/MNE) correspondientes a sesiones de referencia educativa (como repositorios abiertos de elctrofisiología y datos de ejemplo en `data/`).

---

## 4. Casos de Prueba
1. **Consulta conceptual:** Preguntar por las características neurofisiológicas de la banda *alpha*.
2. **Comparación conceptual:** Diferenciar entre los ritmos *theta* y *delta*.
3. **Análisis de señal:** Procesar una señal de ejemplo para identificar la banda de mayor potencia relativa.
4. **Análisis integrado:** Combinar la ejecución de FFT y la consulta teórica para explicar el significado de la señal analizada.
5. **Caso límite:** Realizar una consulta sobre diagnóstico de epilepsia para verificar que el agente reconozca sus limitaciones y rechace el diagnóstico clínico.

---
