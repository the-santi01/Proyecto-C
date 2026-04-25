# Análisis de Rendimiento - Grupo C (HPC)

## Escenario
Estación de Trabajo HPC (High Performance Computing)
Prioridad: Cómputo bruto, FPU potentes, alto ancho de banda

## Datos base del sistema

| Parámetro | Valor |
|-----------|-------|
| Arquitectura | 64 núcleos ARM Neoverse V2 |
| Frecuencia | 3.2 GHz |
| ISA | ARMv9 con SVE2 |
| Ancho de banda memoria | 819 GB/s (HBM3) |

---

## 1. Cálculo de CPI (Ciclos Por Instrucción)

### Desglose por tipo de instrucción

| Tipo de instrucción | Frecuencia | CPI ideal | Penalización | CPI real |
|---------------------|------------|-----------|--------------|----------|
| ALU/FP | 40% | 1.0 | 0 | 1.0 |
| Load/Store | 30% | 1.0 | 2.5 (fallos caché) | 3.5 |
| Vectorial SVE2 | 20% | 0.5 | 0 | 0.5 |
| Saltos/Condicionales | 10% | 1.0 | 0.2 | 1.2 |

### Fórmula y cálculo

### Cálculo del CPI Global
Utilizamos el promedio ponderado de las instrucciones según su frecuencia y penalizaciones:

$$CPI_{total} = \sum (Frecuencia_i \times CPI\_real_i)$$

* $CPI = (0.40 \times 1.0) + (0.30 \times 3.5) + (0.20 \times 0.5) + (0.10 \times 1.2)$
* $CPI = 0.40 + 1.05 + 0.10 + 0.12 = \mathbf{1.67}$

## 2. Cálculo de MIPS (Millones de Instrucciones por Segundo)
Con una frecuencia de **3.2 GHz** por núcleo:

$$MIPS = \frac{3200 \text{ MHz}}{1.67} \approx \mathbf{1,916.16 \text{ MIPS por núcleo}}$$

## 3. Aplicación de la Ley de Amdahl
Para el escenario HPC, evaluamos optimizar el **ancho de banda de memoria** mediante HBM3, lo que impacta directamente en las instrucciones de Load/Store (30% del código).

* **Fracción mejorable ($f$):** 0.30
* **Factor de mejora ($s$):** Supongamos que la memoria HBM3 reduce la latencia a la mitad ($s = 2$).

$$Speedup = \frac{1}{(1 - 0.30) + \frac{0.30}{2}} = \frac{1}{0.7 + 0.15} = \frac{1}{0.85} \approx \mathbf{1.176}$$

**Conclusión:** Una mejora del 100% en la velocidad de memoria resulta en un incremento total del sistema del **17.6%**, demostrando que en HPC, el manejo de datos es tan crítico como la velocidad de cálculo.