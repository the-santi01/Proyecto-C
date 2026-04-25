## Descripción general del escenario

El proyecto consiste en el diseño de una **estación de trabajo HPC (High Performance Computing)** orientada a tareas de alto cómputo como inteligencia artificial, simulaciones científicas y procesamiento de grandes volúmenes de datos.

El enfoque principal es maximizar el rendimiento mediante el uso intensivo de paralelismo, unidades de punto flotante (FPU) y un sistema de memoria de alto ancho de banda que evite cuellos de botella.

---

## Decisiones clave del diseño

### ISA (Arquitectura del Conjunto de Instrucciones)

Se propone una arquitectura optimizada para cómputo intensivo, con soporte eficiente para operaciones de punto flotante y paralelismo, permitiendo un mejor aprovechamiento de múltiples núcleos y aceleradores.

---

### Jerarquía de Memoria

Se implementa una jerarquía de caché en tres niveles (L1, L2, L3) para reducir latencias y mejorar el acceso a datos.
Este diseño permite mantener a las FPU constantemente alimentadas y optimizar el rendimiento en cargas de trabajo intensivas.

---

### Análisis Cuantitativo

El diseño se basa en maximizar el rendimiento (throughput), reduciendo tiempos de acceso a memoria y mejorando la eficiencia del procesamiento.
Se prioriza el balance entre latencia, ancho de banda y paralelismo.

---

### Colaboración en GitHub

El desarrollo del proyecto se gestionó mediante GitHub, utilizando control de versiones para organizar el trabajo en equipo, mantener historial de cambios y facilitar la integración de los distintos componentes del diseño.

---

## 👥 Integrantes del grupo

| No. | Nombre                                   |
|-----|------------------------------------------|
| 1   | Kennet Anderson Santisteban Torres       |
| 2   | Moisés Emanuel Cabrera Noriega           |
| 3   | Oscar David Garcia Larios                |
| 4   | Pablo Matias                            |
| 5   | Andrea Alejandra Lopez Gimenes           |
| 6   | Jonathan Eduardo Jolon Garcia            |