# Plan de Aprendizaje: Estructuras de Datos y Algoritmos para Entrevistas

## 🎯 Objetivo
Dominar patrones de resolución de problemas y estructuras de datos fundamentales para aprobar entrevistas técnicas en empresas top, enfocándose en **calidad sobre cantidad** y **reconocimiento de patrones**.

---

## 📊 Filosofía del Plan

### Principio Clave: Patrones > Problemas Individuales
- No necesitas resolver 1000 problemas
- El 87% de las preguntas de entrevista utilizan 10-15 patrones fundamentales
- Enfócate en **reconocer patrones** y **aplicar plantillas**

### Regla de Complejidad por Dificultad:
- **Easy:** 1 patrón
- **Medium:** 1-2 combinaciones de patrones (ej: two pointers + hashmap)
- **Hard:** 2 patrones, raramente 3

### Enfoque de Aprendizaje
1. **Fundamentos primero** (2-3 semanas)
2. **Patrones por categoría** (8-10 semanas) - **Domina cada patrón resolviendo 5-6 problemas**
3. **Práctica integrada** (continua)
4. **Mock interviews** (últimas 2 semanas)

---

## 🗓️ FASE 1: Fundamentos (Semanas 1-3)

### Semana 1: Big O y Estructuras Básicas

**Teoría (3-4 horas):**
- Notación Big O (tiempo y espacio)
- Arrays y Strings
- Hash Tables/Maps
- Complejidad temporal y espacial

**Práctica diaria (1-2 horas):**
- Día 1-2: Two Sum, Contains Duplicate, Valid Anagram
- Día 3-4: Best Time to Buy and Sell Stock, Product of Array Except Self
- Día 5-7: Group Anagrams, Top K Frequent Elements

**Recursos:**
- Curso Udemy: "Master the Coding Interview: Data Structures + Algorithms"
- NeetCode para problemas agrupados por patrón

### Semana 2: Listas Enlazadas y Stacks/Queues

**Teoría:**
- Linked Lists (Singly, Doubly)
- Stacks (LIFO)
- Queues (FIFO)
- Deques

**Práctica:**
- Reverse Linked List
- Merge Two Sorted Lists
- Valid Parentheses
- Min Stack
- Implement Queue using Stacks

### Semana 3: Árboles y Grafos Básicos

**Teoría:**
- Binary Trees (BST)
- Tree Traversal (Inorder, Preorder, Postorder)
- Graphs (representación)
- BFS y DFS básicos

**Práctica:**
- Invert Binary Tree
- Maximum Depth of Binary Tree
- Same Tree
- Binary Tree Level Order Traversal
- Number of Islands (intro a DFS/BFS en grafos)

---

## 🧩 FASE 2: Dominio de Patrones (Semanas 4-13)

### **Patrón 1: Two Pointers** (Semana 4)

**Cuándo usarlo:**
- Arrays/strings ordenados
- Buscar pares con suma específica
- Eliminar duplicados
- Problemas de palíndromos

**Template básico:**
```python
left, right = 0, len(arr) - 1
while left < right:
    if condition_met:
        # procesar resultado
        left += 1
        right -= 1
    elif need_larger_sum:
        left += 1
    else:
        right -= 1
```

**Variantes del patrón:**
- **Opposite Direction:** Buscar pares en array ordenado (suma objetivo)
- **Same Direction (Fast-Slow):** Detectar ciclos, encontrar elemento medio

**Problemas clave (5-6 mínimo):**
1. Two Sum II (sorted array) - opposite direction
2. 3Sum - opposite direction + loop
3. Container With Most Water - maximize area
4. Remove Duplicates from Sorted Array - same direction
5. Linked List Cycle - fast-slow pointers
6. Happy Number - fast-slow para detectar ciclo

---

### **Patrón 2: Sliding Window** (Semana 5)

**Cuándo usarlo:**
- Subarrays/substrings contiguos
- Máximo/mínimo en ventana
- Problemas con restricciones de tamaño

**Tipos:**
- **Fixed size:** ventana de tamaño k constante
- **Dynamic size:** ventana que crece/decrece según condición

**Template dinámico:**
```python
left = 0
for right in range(len(arr)):
    # agregar elemento a la ventana
    while condicion_invalida:
        # remover elemento izquierdo
        left += 1
    # actualizar resultado con ventana válida
```

**Problemas clave (5-6 mínimo):**
1. Longest Substring Without Repeating Characters - variable + hashset
2. Minimum Window Substring - variable + hashmap (counting)
3. Longest Repeating Character Replacement - variable + counting
4. Maximum Sum Subarray of Size K - fixed window
5. Permutation in String - fixed window + hashmap
6. Sliding Window Maximum - fixed window + deque

---

### **Patrón 3: Fast & Slow Pointers** (Semana 6)

**Cuándo usarlo:**
- Detectar ciclos en linked lists
- Encontrar punto medio
- Problemas de distancia/velocidad

**Problemas clave:**
- Linked List Cycle
- Find the Duplicate Number
- Happy Number
- Middle of the Linked List

---

### **Patrón 4: Merge Intervals** (Semana 7)

**Cuándo usarlo:**
- Intervalos de tiempo que se superponen
- Scheduling problems
- Conflictos de reuniones

**Condición de overlap:**
- `intervalA.end >= intervalB.start`

**Problemas clave:**
- Merge Intervals
- Insert Interval
- Meeting Rooms I & II
- Non-overlapping Intervals

---

### **Patrón 5: Binary Search** (Semana 8)

**Cuándo usarlo:**
- Arrays ordenados
- Buscar elemento específico
- Rotated sorted arrays
- Funciones monótonas

**Template:**
```python
left, right = 0, len(arr) - 1
while left <= right:
    mid = left + (right - left) // 2
    if arr[mid] == target:
        return mid
    elif arr[mid] < target:
        left = mid + 1
    else:
        right = mid - 1
```

**Problemas clave (5-6 mínimo):**
1. Binary Search (clásico)
2. Search in Rotated Sorted Array - rotated array search
3. Find Minimum in Rotated Sorted Array - peak finding
4. Search a 2D Matrix - matrix search
5. Koko Eating Bananas - binary search on answer
6. Find Peak Element - peak finding variant

---

### **Patrón 6: DFS en Árboles** (Semana 9)

**Cuándo usarlo:**
- Explorar todas las ramas
- Path problems
- Validación de árboles

**Tipos:**
- Preorder (raíz → izq → der)
- Inorder (izq → raíz → der)
- Postorder (izq → der → raíz)

**Problemas clave (5-6 mínimo):**
1. Path Sum - path exploration
2. Diameter of Binary Tree - postorder calculation
3. Lowest Common Ancestor - ancestor finding
4. Validate Binary Search Tree - inorder validation
5. Maximum Path Sum - path with negative values
6. Count Good Nodes in Binary Tree - preorder with tracking

---

### **Patrón 7: BFS en Árboles/Grafos** (Semana 10)

**Cuándo usarlo:**
- Level-order traversal
- Shortest path (grafos no ponderados)
- Todos los nodos a cierta distancia

**Template:**
```python
from collections import deque
queue = deque([root])
while queue:
    level_size = len(queue)
    for _ in range(level_size):
        node = queue.popleft()
        # procesar nodo
        if node.left: queue.append(node.left)
        if node.right: queue.append(node.right)
```

**Problemas clave (5-6 mínimo):**
1. Binary Tree Level Order Traversal - level traversal básico
2. Binary Tree Zigzag Level Order - level con modificación
3. Rotting Oranges - BFS en matriz (multi-source)
4. Word Ladder - BFS para shortest path
5. Clone Graph - BFS con visited tracking
6. Number of Islands - puede resolverse con BFS también

**Complejidad:** O(V + E) donde V = vértices, E = aristas

---

### **Patrón 8: Dynamic Programming** (Semanas 11-12)

**Cuándo usarlo:**
- Problemas de optimización
- Contar formas de hacer algo
- Subproblemas superpuestos

**Enfoques:**
- **Top-down (Memoization):** recursión + cache
- **Bottom-up (Tabulation):** iterativo, llenar tabla

**Subpatrones:**
1. **1D DP:** Fibonacci, House Robber, Climbing Stairs
2. **2D DP:** Unique Paths, Longest Common Subsequence
3. **Knapsack:** 0/1 Knapsack, Partition Equal Subset Sum

**Problemas clave (5-6 mínimo):**
1. Climbing Stairs - 1D DP básico (Fibonacci pattern)
2. House Robber - 1D DP con decisión skip/take
3. Coin Change - 1D DP unbounded knapsack
4. Longest Increasing Subsequence - 1D DP sequence
5. Unique Paths - 2D DP grid
6. Longest Common Subsequence - 2D DP strings

**Enfoque Top-Down vs Bottom-Up:**
- **Top-down:** Más intuitivo, usa recursión + memoization
- **Bottom-up:** Más eficiente en espacio, usa tabla iterativa

---

### **Patrón 9: Backtracking** (Semana 13)

**Cuándo usarlo:**
- Generar todas las combinaciones/permutaciones
- Problemas de decisión (tomar/no tomar)
- Sudoku, N-Queens

**Template:**
```python
def backtrack(path, opciones):
    if es_solucion_completa(path):
        resultado.append(path[:])
        return
    
    for opcion in opciones:
        # elegir
        path.append(opcion)
        # explorar
        backtrack(path, nuevas_opciones)
        # deshacer
        path.pop()
```

**Problemas clave (5-6 mínimo):**
1. Subsets - generar todas las combinaciones
2. Permutations - generar todos los ordenamientos
3. Combination Sum - decisión con repetición
4. Letter Combinations of Phone Number - múltiples opciones por nivel
5. N-Queens - constraint satisfaction
6. Word Search - backtracking en matriz

---

## 🔥 FASE 3: Patrones Avanzados y de Arrays (Semanas 14-16)

### **Patrón 10: Top K Elements (Heaps)**

**Cuándo usarlo:**
- Problemas con "K largest/smallest"
- Mantener top K elementos
- Streaming data

**Conceptos clave:**
- **Min Heap:** Encuentra K largest (mantiene los K más grandes, elimina pequeños)
- **Max Heap:** Encuentra K smallest (mantiene los K más pequeños, elimina grandes)

**Problemas:** 
- Kth Largest Element in Array
- Top K Frequent Elements
- Find Median from Data Stream
- K Closest Points to Origin
- Kth Largest Element in Stream

---

### **Patrón 11: Monotonic Stack**

**Cuándo usarlo:**
- Next greater/smaller element
- Problemas de comparación con elementos previos
- Mantener orden específico

**Problemas:**
- Next Greater Element I & II
- Daily Temperatures
- Largest Rectangle in Histogram
- Trapping Rain Water (alternativa a two pointers)

---

### **Patrón 12: Prefix Sum & HashMap**

**Cuándo usarlo:**
- Subarrays con suma específica
- Range sum queries
- Subarray que cumple condición

**Problemas:**
- Subarray Sum Equals K
- Continuous Subarray Sum
- Product of Array Except Self (prefix/suffix)
- Range Sum Query

---

### **Patrón 13: Arrays - Patrones Adicionales**

**13.1 Array Rotation**
- Rotate Array
- Rotate Image (Matrix)

**13.2 Kadane's Algorithm (Maximum Subarray)**
- Maximum Subarray Sum
- Maximum Product Subarray

**13.3 Sort + Greedy**
- Meeting Rooms (intervals)
- Assign Cookies
- Jump Game

**13.4 HashSet (Existence Check)**
- Contains Duplicate
- Longest Consecutive Sequence

**13.5 Matrix Patterns**
- Spiral Matrix
- Set Matrix Zeroes
- Search a 2D Matrix II

---

### **Patrón 14: Algoritmos de Sorting (Conocimiento Teórico)**

**Insertion Sort:**
- O(n²) worst case, O(n) best case
- Bueno para listas pequeñas o casi ordenadas

**Merge Sort:**
- O(n log n) siempre (estable)
- Divide and conquer
- Útil para: Count of Smaller Numbers After Self, Reverse Pairs

**Quick Sort:**
- O(n log n) average, O(n²) worst case
- In-place sorting
- Útil para: Kth Largest Element (QuickSelect)

**Nota:** Raramente necesitas implementarlos desde cero en entrevistas, pero debes conocer sus complejidades.

---

### **Patrón 15: Union Find (Disjoint Set) - Opcional**
- Number of Connected Components
- Redundant Connection
- Accounts Merge

---

### **Patrón 16: Trie - Opcional**
- Implement Trie
- Word Search II
- Design Add and Search Words Data Structure

---

### **Patrón 17: Greedy Algorithms**

**Cuándo usarlo:**
- Optimización con elección local óptima
- Scheduling problems
- Shortest path en grafos (Dijkstra)

**Ejemplos:**
- Jump Game I & II
- Gas Station
- Partition Labels
- Dijkstra's Algorithm (shortest path con pesos)

---

## 📈 FASE 4: Integración y Mock Interviews (Semanas 17-18)

### Objetivos:
1. **Resolver problemas mixtos** sin saber el patrón de antemano
2. **Practicar explicación verbal** del approach
3. **Optimizar soluciones** (tiempo y espacio)
4. **Mock interviews** en Pramp, interviewing.io

### Rutina diaria:
- 1 problema Medium sin ver solución (45 min)
- 1 problema de patrón débil (30 min)
- Revisar 2-3 soluciones de otros (15 min)

---

## 📚 Recursos Recomendados

### Plataformas de Práctica:
1. **NeetCode.io** - Problemas agrupados por patrón (⭐ MEJOR PARA EMPEZAR)
2. **LeetCode** - 75 problemas de Blind 75 / Grind 75
3. **AlgoMonster** - Enfoque por patrones

### Cursos:
- **Grokking the Coding Interview** (DesignGurus.io)
- **Master the Coding Interview** (Udemy - Andrei Neagoie)

### Para Referencia Rápida:
- Tech Interview Handbook (gratis)
- 14 Patterns by Sean Prashad

---

## 🎯 Estrategia de Resolución de Problemas

### Antes de Codear (5-10 min):
1. **Clarifica el problema** - inputs, outputs, edge cases
2. **Ejemplos manuales** - crea 2-3 casos de prueba
3. **Identifica el patrón** - ¿qué estructura/algoritmo se parece?
4. **Discute el approach** - explica la idea antes de codear
5. **Analiza complejidad** - O(n)? O(n²)? espacio extra?

### Al Codear:
- Usa nombres de variables descriptivos
- Comenta secciones complejas
- Testea con ejemplos mientras escribes

### Después de Codear:
- Verifica edge cases ([], [1], valores negativos)
- Optimiza si es posible
- Explica trade-offs

---

## 📊 Métricas de Progreso

### Semanas 1-3:
- ✅ 15-20 problemas Easy resueltos
- ✅ Entiendes Big O intuitivamente

### Semanas 4-13:
- ✅ 2-3 problemas por patrón (mínimo)
- ✅ Puedes identificar el patrón en 2-3 minutos
- ✅ 60-80 problemas total (Easy + Medium)

### Semanas 14-18:
- ✅ 100+ problemas resueltos
- ✅ 70% de éxito en problemas Medium
- ✅ Puedes explicar 3 approaches diferentes para mismo problema

---

## 💡 Tips Clave

1. **No memorices soluciones** - entiende el "por qué" del patrón
2. **Regla 5-6 problemas:** Domina cada patrón resolviendo 5-6 problemas antes de avanzar
3. **1-2 horas diarias > maratones de fin de semana**
4. **Si estás atascado 30+ min** - ve la solución, entiéndela, resuélvela de nuevo mañana
5. **Practica explicar en voz alta** - simula la entrevista
6. **Revisa problemas antiguos** cada 2 semanas (spaced repetition)
7. **Lenguaje:** Elige Python (sintaxis clara) o el que domines mejor
8. **Usa IA como tutor:** Herramientas de IA pueden explicar conceptos rápidamente y ahorrarte tiempo
9. **Identifica patrones por keywords:** Aprende a reconocer qué patrón aplicar según palabras clave y restricciones del problema

---

## ⚠️ Errores Comunes a Evitar

❌ Hacer 500 problemas random sin patrón  
❌ Solo ver soluciones sin intentar primero  
❌ No practicar comunicación verbal  
❌ Ignorar complejidad temporal/espacial  
❌ No revisar problemas resueltos previamente  

---

## 🏆 Checklist Final Pre-Entrevista

- [ ] Puedo identificar 12+ patrones en 2-3 minutos
- [ ] He resuelto al menos 100 problemas (70% Medium)
- [ ] Puedo explicar mi approach claramente
- [ ] Conozco complejidades de operaciones en todas las estructuras
- [ ] He hecho 5+ mock interviews
- [ ] Puedo codear sin IDE (whiteboard/papel)

---

**¡Éxito en tus entrevistas! 🚀 La consistencia es la clave.**