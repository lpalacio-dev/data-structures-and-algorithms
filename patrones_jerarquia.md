# Jerarquía y Relación de Patrones DSA

## 🎯 Organización: Patrones Fundamentales vs Especializados

---

## 📊 ESTRUCTURA JERÁRQUICA

```
8 PATRONES FUNDAMENTALES (Core Concepts)
│
├── Aplicaciones Específicas en Arrays (21 patrones)
├── Aplicaciones en Strings
├── Aplicaciones en Linked Lists
├── Aplicaciones en Trees
└── Aplicaciones en Graphs
```

---

## 🔵 PATRONES FUNDAMENTALES (8 Core)

Estos son los **conceptos algorítmicos universales** que se aplican a múltiples estructuras de datos:

### 1. **Two Pointers** 🎯
- **Concepto fundamental:** Usar 2 índices para recorrer datos
- **Complejidad:** O(n)

#### Aplicaciones específicas en Arrays:
- ✅ **Patrón 2:** Two Pointers (Opposite Direction)
- ✅ **Patrón 3:** Two Pointers (Same Direction / Fast-Slow)
- ✅ **Patrón 11:** Sort + Two Pointers (combinación)

---

### 2. **Sliding Window** 🪟
- **Concepto fundamental:** Ventana dinámica sobre datos contiguos
- **Complejidad:** O(n)
- **Relación:** Es una **especialización avanzada de Two Pointers**

#### Aplicaciones específicas en Arrays:
- ✅ **Patrón 8:** Sliding Window - Variable
- ✅ **Patrón 9:** Sliding Window - Fixed

---

### 3. **Binary Search** 🔍
- **Concepto fundamental:** Búsqueda logarítmica en datos ordenados/monótonos
- **Complejidad:** O(log n)

#### Aplicaciones específicas en Arrays:
- ✅ **Patrón 14:** Classic Binary Search
- ✅ **Patrón 15:** Peak Finding (Binary Search)
- ✅ **Patrón 16:** Rotated Sorted Array Search
- ✅ **Patrón 17:** Binary Search on Answer
- ✅ **Patrón 19:** Matrix Search (BS en 2D)

---

### 4. **BFS (Breadth-First Search)** 🌊
- **Concepto fundamental:** Exploración nivel por nivel
- **Complejidad:** O(V + E)
- **Estructura auxiliar:** Queue

#### Aplicaciones específicas:
- ❌ **NO aplica directamente a arrays simples**
- ✅ Aplica a: Trees (level-order), Graphs, Matrices como grafos
- ✅ **Patrón 18:** Matrix Traversal (puede usar BFS)

---

### 5. **DFS (Depth-First Search)** 🏔️
- **Concepto fundamental:** Exploración profunda recursiva
- **Complejidad:** O(V + E)
- **Estructura auxiliar:** Stack (implícito en recursión)

#### Aplicaciones específicas:
- ❌ **NO aplica directamente a arrays simples**
- ✅ Aplica a: Trees, Graphs, Backtracking
- ✅ **Patrón 18:** Matrix Traversal (puede usar DFS)
- ✅ **Patrón 20:** Matrix Modification (ej: Flood Fill con DFS)

---

### 6. **Backtracking** 🔄
- **Concepto fundamental:** DFS + decisiones + deshacer
- **Complejidad:** O(2^n) o O(n!)
- **Relación:** Es una **especialización de DFS**

#### Aplicaciones específicas:
- ❌ **NO aplica directamente a arrays simples**
- ✅ Aplica a: Generar combinaciones, permutaciones, subsets
- ⚠️ Ninguno de los 21 patrones de arrays usa backtracking puro
  - (Backtracking es más común en problemas de "generar todas las soluciones")

---

### 7. **Priority Queue (Heap)** 📊
- **Concepto fundamental:** Mantener elementos ordenados parcialmente
- **Complejidad:** O(log n) insert/delete, O(1) peek
- **Estructura:** Min-heap o Max-heap

#### Aplicaciones específicas:
- ❌ **NO está en los 21 patrones básicos de arrays**
- ✅ Se usa en: Top K Elements, Median Stream, Dijkstra
- 💡 Es un patrón **avanzado** que aparece después de dominar arrays

---

### 8. **Dynamic Programming (DP)** 💎
- **Concepto fundamental:** Optimización con subproblemas superpuestos
- **Complejidad:** Varía (O(n), O(n²), etc.)
- **Enfoques:** Top-down (memoization) o Bottom-up (tabulation)

#### Aplicaciones específicas:
- ✅ **Patrón 7:** Kadane's Algorithm (caso especial de DP 1D)
- ✅ **Patrón 10:** Prefix Sum + HashMap (relacionado con DP)
- ⚠️ DP completo es **avanzado**, no está en patrones básicos de arrays

---

## 🟢 PATRONES AUXILIARES (Técnicas de Soporte)

Estos NO son algoritmos principales, sino **técnicas que se combinan** con los patrones fundamentales:

### 9. **HashSet (Existence)** 🗂️
- **Tipo:** Estructura de datos auxiliar
- **Uso:** Verificar existencia en O(1)
- ✅ **Patrón 5:** HashSet (Existence)
- 🔗 Se combina con: Two Pointers, Sliding Window, etc.

### 10. **HashMap (Counting/Frequency)** 📈
- **Tipo:** Estructura de datos auxiliar
- **Uso:** Contar frecuencias en O(1)
- ✅ **Patrón 6:** HashMap (Counting / Frequency)
- ✅ **Patrón 10:** Prefix Sum + HashMap (combinación)
- 🔗 Se combina con: Sliding Window, Two Pointers, etc.

### 11. **Simple Traversal** 🚶
- **Tipo:** Técnica básica
- **Complejidad:** O(n)
- ✅ **Patrón 1:** Simple Traversal
- 💡 Es el "building block" más básico

### 12. **Sorting** 📊
- **Tipo:** Preprocessing technique
- **Complejidad:** O(n log n)
- ✅ **Patrón 11:** Sort + Two Pointers
- ✅ **Patrón 12:** Sort + Greedy
- ✅ **Patrón 13:** Modified Merge Sort
- 🔗 Se usa como **paso previo** para aplicar otros patrones

### 13. **Array Rotation** 🔄
- **Tipo:** Técnica específica de arrays
- ✅ **Patrón 4:** Array Rotation
- 💡 Usa reverse 3 veces (técnica ingeniosa)

### 14. **Prefix/Suffix** 📊
- **Tipo:** Técnica de precómputo
- ✅ **Patrón 10:** Prefix Sum + HashMap
- ✅ **Patrón 21:** Prefix/Suffix Products
- 🔗 Relacionado con DP (optimización)

### 15. **Matrix Patterns** 🎲
- **Tipo:** Aplicación 2D de técnicas básicas
- ✅ **Patrón 18:** Matrix Traversal
- ✅ **Patrón 19:** Matrix Search
- ✅ **Patrón 20:** Matrix Modification
- 🔗 Usa: DFS, BFS, Two Pointers, Binary Search

---

## 🎓 MAPA DE RELACIONES

### Nivel 1: Conceptos Fundamentales Universales (8 Core)
```
1. Two Pointers       → Base para muchos patrones lineales
2. Sliding Window     → Especialización de Two Pointers
3. Binary Search      → Para datos ordenados/monótonos
4. BFS                → Exploración por niveles
5. DFS                → Exploración en profundidad
6. Backtracking       → DFS + decisiones
7. Heap               → Mantener top K, mediana
8. Dynamic Programming → Optimización con subproblemas
```

### Nivel 2: Técnicas Auxiliares
```
- HashSet/HashMap     → Complementan patrones principales
- Sorting             → Preprocesamiento
- Prefix/Suffix       → Optimización de rangos
- Simple Traversal    → Building block básico
```

### Nivel 3: Aplicaciones Específicas en Arrays (21 patrones)
```
Patrones que son aplicaciones/combinaciones de los conceptos Level 1 y 2
```

---

## 📋 TABLA DE CORRESPONDENCIA COMPLETA

| **21 Patrones de Arrays** | **Patrón Fundamental** | **Relación** |
|---------------------------|------------------------|--------------|
| 1. Simple Traversal | - | Técnica básica |
| 2. Two Pointers (Opposite) | Two Pointers | Aplicación directa |
| 3. Two Pointers (Same/Fast-Slow) | Two Pointers | Aplicación directa |
| 4. Array Rotation | - | Técnica específica de arrays |
| 5. HashSet (Existence) | - | Estructura auxiliar |
| 6. HashMap (Counting) | - | Estructura auxiliar |
| 7. Kadane's Algorithm | Dynamic Programming | DP 1D especializado |
| 8. Sliding Window - Variable | Sliding Window | Aplicación directa |
| 9. Sliding Window - Fixed | Sliding Window | Aplicación directa |
| 10. Prefix Sum + HashMap | Dynamic Programming / HashMap | Combinación |
| 11. Sort + Two Pointers | Two Pointers + Sorting | Combinación |
| 12. Sort + Greedy | - | Sorting + elección local |
| 13. Modified Merge Sort | Sorting | Merge Sort modificado |
| 14. Classic Binary Search | Binary Search | Aplicación directa |
| 15. Peak Finding | Binary Search | Variante de BS |
| 16. Rotated Sorted Array | Binary Search | Variante de BS |
| 17. Binary Search on Answer | Binary Search | Aplicación avanzada |
| 18. Matrix Traversal | DFS / BFS | Aplicación en 2D |
| 19. Matrix Search | Binary Search | BS en 2D |
| 20. Matrix Modification | DFS | DFS en 2D (ej: Flood Fill) |
| 21. Prefix/Suffix Products | - | Técnica de precómputo |

---

## 🎯 CÓMO ORGANIZAR TU APRENDIZAJE

### Fase 1: Domina los 8 Fundamentales (conceptualmente)
Entiende **qué son, cuándo usarlos, y por qué funcionan**:
1. Two Pointers
2. Sliding Window
3. Binary Search
4. BFS
5. DFS
6. Backtracking
7. Heap
8. DP

### Fase 2: Aplica los Fundamentales a Arrays (21 patrones)
**Practica cómo se implementan en arrays específicamente:**
- Two Pointers → Patrones 2, 3, 11
- Sliding Window → Patrones 8, 9
- Binary Search → Patrones 14, 15, 16, 17, 19
- DFS/BFS → Patrones 18, 20
- DP → Patrones 7, 10, 21

### Fase 3: Transfiere a otras estructuras
- Two Pointers en Linked Lists
- Sliding Window en Strings
- BFS/DFS en Trees y Graphs

---

## 💡 INSIGHT CLAVE

### Los 8 patrones fundamentales son **CONCEPTOS**
- Son ideas algorítmicas que trascienden estructuras de datos
- Aprenderlos una vez te permite aplicarlos everywhere

### Los 21 patrones de arrays son **IMPLEMENTACIONES**
- Son formas específicas de aplicar los 8 fundamentales a arrays
- Incluyen técnicas auxiliares (HashSet, Sorting, etc.)

### Analogía:
```
8 Fundamentales = Principios de Física
21 Patrones Arrays = Cómo construir puentes con esos principios
```

---

## 🚀 ORDEN DE APRENDIZAJE RECOMENDADO

### Opción A: Bottom-Up (Recomendado para beginners)
1. Aprende los 21 patrones de arrays (implementación concreta)
2. Luego abstrae los 8 conceptos fundamentales
3. Aplica a otras estructuras

**Ventaja:** Aprendes haciendo, no solo teoría

### Opción B: Top-Down (Para quienes prefieren teoría primero)
1. Estudia los 8 patrones fundamentales (conceptos)
2. Practica cada uno en arrays
3. Expande a otras estructuras

**Ventaja:** Visión completa desde el inicio

---

## 📊 RESUMEN VISUAL

```
8 PATRONES FUNDAMENTALES (Core Algorithms)
════════════════════════════════════════════
    ↓ aplicados a ↓
    
ARRAYS (21 implementaciones específicas)
════════════════════════════════════════════
1-3:   Two Pointers (3 variantes)
4:     Array Rotation (técnica única)
5-6:   Hash structures (auxiliares)
7:     Kadane's (DP especializado)
8-9:   Sliding Window (2 variantes)
10:    Prefix Sum (DP + HashMap)
11-13: Sorting combinado
14-17: Binary Search (4 variantes)
18-20: Matrix (DFS/BFS en 2D)
21:    Prefix/Suffix (precómputo)

    ↓ se transfieren a ↓
    
STRINGS, LINKED LISTS, TREES, GRAPHS
════════════════════════════════════════════
Mismos 8 fundamentales, diferentes contextos
```

---

## ✅ CONCLUSIÓN

**Los 21 patrones NO son independientes de los 8 fundamentales.**

Son **aplicaciones, combinaciones y especializaciones** de los 8 conceptos algorítmicos universales, más técnicas auxiliares específicas de arrays.

**Dominar arrays con los 21 patrones ≈ Dominar los 8 fundamentales en un contexto concreto**

Cuando pases a otras estructuras, reconocerás: "Oh, esto es Binary Search pero en un árbol" o "Two Pointers pero en linked list".