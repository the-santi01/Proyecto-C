# Diseño de Jerarquía de Memoria - Estación HPC

## 1. Objetivo del Diseño

El objetivo es diseñar una jerarquía de memoria optimizada para una estación HPC, priorizando el cómputo intensivo en punto flotante (FPU), el paralelismo y el alto ancho de banda.

Según Hennessy & Patterson (2025), los sistemas HPC priorizan el throughput sobre la latencia individual, por lo que la memoria debe alimentar constantemente a las unidades de ejecución.

---

## 2. Jerarquía de Caché

### Caché L1

* Tamaño: 64 KB por núcleo (32 KB instrucciones + 32 KB datos)
* Latencia: 1–2 ciclos
* Tipo: Privada
* Política de reemplazo: LRU

Justificación: Proporciona acceso inmediato a datos críticos para la FPU.

---

### Caché L2

* Tamaño: 512 KB – 1 MB por núcleo
* Latencia: 4–10 ciclos
* Tipo: Privada
* Política: Pseudo-LRU

Justificación: Reduce accesos a niveles superiores y mantiene datos intermedios.

---

### Caché L3

* Tamaño: 32 MB – 128 MB compartida
* Latencia: 30–50 ciclos
* Tipo: Compartida
* Política: LRU adaptativo

Justificación: Permite compartir datos entre núcleos y reduce accesos a memoria principal.

---

## 3. Políticas de Reemplazo

* L1: LRU
* L2: Pseudo-LRU
* L3: LRU adaptativo / LFU

Según Stallings (2015), estas políticas permiten balancear rendimiento y costo en sistemas multinúcleo.

---

## 4. Inclusividad de Caché

Se propone una caché no inclusiva (Non-Inclusive), para evitar duplicación de datos y mejorar el uso del espacio.

---

## 5. Coherencia de Caché

Se implementa el protocolo MESI/MOESI para garantizar consistencia entre núcleos.

---

## 6. Ancho de Banda

Se considera el uso de memoria de alto ancho de banda (HBM) y buses de alta velocidad para evitar cuellos de botella.

---

## 7. Conclusión

El diseño propuesto optimiza el rendimiento en entornos HPC mediante:

* Reducción de latencia
* Alto ancho de banda
* Soporte para paralelismo masivo

Esto permite un uso eficiente de las unidades FPU en aplicaciones científicas e inteligencia artificial.
