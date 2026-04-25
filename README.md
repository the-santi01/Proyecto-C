## Descripción general del escenario

El proyecto consiste en el diseño de una **estación de trabajo HPC (High Performance Computing)** orientada a tareas de alto cómputo como inteligencia artificial, simulaciones científicas y procesamiento de grandes volúmenes de datos.

El enfoque principal es maximizar el rendimiento mediante el uso intensivo de paralelismo, unidades de punto flotante (FPU) y un sistema de memoria de alto ancho de banda que evite cuellos de botella.

---

## Decisiones clave del diseño

### ISA (Arquitectura del Conjunto de Instrucciones)

Se propone una arquitectura optimizada para cómputo intensivo, con soporte eficiente para operaciones de punto flotante y paralelismo, permitiendo un mejor aprovechamiento de múltiples núcleos y aceleradores.

---

### Jerarquía de Memoria

Se implementa una jerarquía de caché en tres niveles (L1, L2, L3) para reducir latencias y mejorar el acceso a datos. Este diseño permite mantener a las FPU constantemente alimentadas y optimizar el rendimiento en cargas de trabajo intensivas.

La caché L1, ubicada más cerca del núcleo del procesador, ofrece el acceso más rápido y está orientada a almacenar instrucciones y datos críticos de uso inmediato. La caché L2 proporciona un mayor tamaño con una ligera penalización en latencia, funcionando como un nivel intermedio que reduce accesos frecuentes a memoria principal. Por su parte, la caché L3 es compartida entre múltiples núcleos, permitiendo una mejor coordinación y reutilización de datos en entornos multinúcleo.

En el contexto HPC, esta jerarquía es fundamental, ya que el rendimiento no depende únicamente de la velocidad del procesador, sino de la capacidad de suministrar datos de forma constante a las unidades de ejecución. Una mala gestión de memoria puede generar cuellos de botella que limiten el paralelismo, mientras que una jerarquía optimizada permite maximizar el throughput del sistema.

---

### Análisis Cuantitativo

El diseño se basa en maximizar el rendimiento (throughput), reduciendo tiempos de acceso a memoria y mejorando la eficiencia del procesamiento.
Se prioriza el balance entre latencia, ancho de banda y paralelismo.

---

## Colaboración en GitHub

El desarrollo del proyecto se gestionó mediante GitHub, utilizando control de versiones para organizar el trabajo en equipo, mantener un historial detallado de cambios y facilitar la integración de los distintos componentes del diseño.


El uso de commits descriptivos permitió llevar un control claro de las modificaciones realizadas, facilitando la trazabilidad y la identificación de cambios específicos en el desarrollo del proyecto.

Además, GitHub permitió:
- Centralizar la documentación 
- Evitar conflictos mediante la actualización constante del repositorio 
- Mantener versiones estables del proyecto

En conjunto, estas prácticas aseguraron un flujo de trabajo eficiente, organizado y alineado con metodologías modernas de desarrollo colaborativo.
---

## 👥 Integrantes del grupo

| No. | Nombre                                   |
|-----|------------------------------------------|
| 1   | Kennet Anderson Santisteban Torres       |
| 2   | Moisés Emanuel Cabrera Noriega           |
| 3   | Oscar David Garcia Larios                |
| 4   | Pablo Matias                            |
| 5   | Andrea Alejandra Lopez Jimenez           |
| 6   | Jonathan Eduardo Jolon Garcia            |
