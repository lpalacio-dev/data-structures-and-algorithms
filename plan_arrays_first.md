# Plan DSA: Dominio por Estructura de Datos (Arrays First)

## 🎯 Filosofía del Enfoque

### Principio Fundamental: Maestría Standalone por Estructura de Datos
**En lugar de aprender "todos los patrones" mezclados, dominas una estructura de datos a la vez con TODOS sus patrones.**

### Regla de Complejidad
- **Easy:** 1 patrón
- **Medium:** 1-2 combinaciones de patrones (ej: two pointers + hashmap)
- **Hard:** 2 patrones, raramente 3

### Metodología
1. **Elige una estructura de datos** (empezar con Arrays)
2. **Domina cada patrón:** resuelve 5-6 problemas por patrón
3. **Reconoce keywords** que indican qué patrón aplicar
4. **Usa IA como tutor** para explicaciones rápidas
5. **Solo después de dominar completamente una estructura**, pasa a la siguiente

---

## 📚 Ruta de Aprendizaje: Estructura por Estructura

### Secuencia Recomendada:
1. **Arrays** (6-8 semanas) ← EMPIEZA AQUÍ
2. **Strings** (2-3 semanas)
3. **Linked Lists** (2 semanas)
4. **Stacks & Queues** (1-2 semanas)
5. **Trees** (3-4 semanas)
6. **Graphs** (2-3 semanas)
7. **Estructuras Avanzadas** (2-3 semanas) - Heaps, Tries, etc.

**Total:** ~16-20 semanas para dominio completo

---

## 🔥 FASE 1: ARRAYS (Semanas 1-8)

### Por qué empezar con Arrays:
- Es la estructura más común en entrevistas (~40% de problemas)
- Muchos patrones se transfieren a otras estructuras
- Si dominas los 21 patrones de arrays, **ya estás interview-ready para muchas empresas**

---

### **Patrón 1: Simple Traversal** (Día 1-2)

**Cuándo usarlo:**
- Necesitas visitar cada elemento una vez
- Operaciones básicas: suma, promedio, búsqueda lineal

**Template:**
```python
for i in range(len(arr)):
    # procesar arr[i]
```

**Keywords:** "iterate", "visit all", "sum of elements", "find element"

**Problemas (5-6):**
1. Running Sum of 1D Array (LC 1480)
2. Find Numbers with Even Number of Digits (LC 1295)
3. Richest Customer Wealth (LC 1672)
4. Maximum Count of Positive Integer and Negative Integer (LC 2529)
5. Count Negative Numbers in Sorted Matrix (LC 1351)
6. Average Salary Excluding Min and Max (LC 1491)

---

### **Patrón 2: Two Pointers (Opposite Direction)** (Días 3-5)

**Cuándo usarlo:**
- Array **ordenado**
- Buscar pares con suma/producto específico
- Comparar elementos desde extremos

**Template:**
```python
left, right = 0, len(arr) - 1
while left < right:
    if arr[left] + arr[right] == target:
        # found pair
        left += 1
        right -= 1
    elif arr[left] + arr[right] < target:
        left += 1
    else:
        right -= 1
```

**Keywords:** "sorted array", "pair sum", "two elements", "opposite ends"

**Problemas (5-6):**
1. Two Sum II - Input Array Is Sorted (LC 167)
2. 3Sum (LC 15)
3. Container With Most Water (LC 11)
4. Valid Palindrome (LC 125) - aplicable a strings
5. Trapping Rain Water (LC 42)
6. Sort Colors (LC 75) - Dutch National Flag

---

### **Patrón 3: Two Pointers (Same Direction / Fast-Slow)** (Días 6-8)

**Cuándo usarlo:**
- Remover elementos in-place
- Detectar ciclos
- Encontrar elemento duplicado
- Modificar array sin espacio extra

**Template:**
```python
slow = 0
for fast in range(len(arr)):
    if condition:
        arr[slow] = arr[fast]
        slow += 1
return slow  # nuevo tamaño
```

**Keywords:** "in-place", "remove duplicates", "without extra space", "detect cycle"

**Problemas (5-6):**
1. Remove Duplicates from Sorted Array (LC 26)
2. Remove Element (LC 27)
3. Move Zeroes (LC 283)
4. Linked List Cycle (LC 141) - aplicable a linked lists
5. Find the Duplicate Number (LC 287)
6. Happy Number (LC 202)

---

### **Patrón 4: Array Rotation** (Días 9-10)

**Cuándo usarlo:**
- Rotar array k posiciones
- Reverse en segmentos

**Técnica clave:** Reverse 3 veces
```python
# Rotar k a la derecha
reverse(arr, 0, n-1)      # reverse todo
reverse(arr, 0, k-1)      # reverse primeros k
reverse(arr, k, n-1)      # reverse resto
```

**Keywords:** "rotate", "shift", "circular"

**Problemas (5-6):**
1. Rotate Array (LC 189)
2. Rotate Image (LC 48) - matriz
3. Reverse String (LC 344)
4. Reverse Words in a String (LC 151)
5. Rotate String (LC 796)
6. Reverse Words in a String III (LC 557)

---

### **Patrón 5: HashSet (Existence Check)** (Días 11-12)

**Cuándo usarlo:**
- Verificar si elemento existe
- Encontrar duplicados
- Problemas de intersección/unión

**Template:**
```python
seen = set()
for num in arr:
    if num in seen:
        return True  # duplicado encontrado
    seen.add(num)
```

**Keywords:** "contains", "duplicate", "unique", "exists"

**Problemas (5-6):**
1. Contains Duplicate (LC 217)
2. Single Number (LC 136)
3. Intersection of Two Arrays (LC 349)
4. Missing Number (LC 268)
5. Find All Numbers Disappeared in Array (LC 448)
6. Longest Consecutive Sequence (LC 128)

---

### **Patrón 6: HashMap (Counting / Frequency)** (Días 13-15)

**Cuándo usarlo:**
- Contar frecuencias
- Agrupar elementos
- Problemas de anagrams

**Template:**
```python
from collections import Counter, defaultdict
freq = Counter(arr)
# o manualmente:
freq = {}
for num in arr:
    freq[num] = freq.get(num, 0) + 1
```

**Keywords:** "frequency", "count", "group", "anagram", "majority element"

**Problemas (5-6):**
1. Two Sum (LC 1)
2. Majority Element (LC 169)
3. Valid Anagram (LC 242)
4. Group Anagrams (LC 49)
5. Top K Frequent Elements (LC 347)
6. First Unique Character in String (LC 387)

---

### **Patrón 7: Kadane's Algorithm (Maximum Subarray)** (Días 16-17)

**Cuándo usarlo:**
- Maximum/minimum subarray sum
- Máximo producto de subarray

**Template:**
```python
max_sum = current_sum = arr[0]
for i in range(1, len(arr)):
    current_sum = max(arr[i], current_sum + arr[i])
    max_sum = max(max_sum, current_sum)
return max_sum
```

**Keywords:** "maximum subarray", "contiguous", "largest sum"

**Problemas (5-6):**
1. Maximum Subarray (LC 53)
2. Maximum Product Subarray (LC 152)
3. Maximum Sum Circular Subarray (LC 918)
4. Best Time to Buy and Sell Stock (LC 121)
5. Maximum Average Subarray I (LC 643)
6. Longest Turbulent Subarray (LC 978)

---

### **Patrón 8: Sliding Window - Variable Size** (Días 18-20)

**Cuándo usarlo:**
- Substring/subarray más largo/corto que cumple condición
- Ventana que crece/decrece dinámicamente

**Template:**
```python
left = 0
result = 0
for right in range(len(arr)):
    # agregar arr[right] a ventana
    while ventana_invalida():
        # remover arr[left]
        left += 1
    # actualizar resultado con ventana válida
    result = max(result, right - left + 1)
```

**Keywords:** "longest", "shortest", "minimum", "substring", "at most K"

**Problemas (5-6):**
1. Longest Substring Without Repeating Characters (LC 3)
2. Minimum Size Subarray Sum (LC 209)
3. Longest Repeating Character Replacement (LC 424)
4. Max Consecutive Ones III (LC 1004)
5. Fruit Into Baskets (LC 904)
6. Minimum Window Substring (LC 76)

---

### **Patrón 9: Sliding Window - Fixed Size** (Días 21-22)

**Cuándo usarlo:**
- Ventana de tamaño K constante
- Maximum/minimum en ventana fija

**Template:**
```python
window_sum = sum(arr[:k])
max_sum = window_sum
for i in range(k, len(arr)):
    window_sum += arr[i] - arr[i - k]
    max_sum = max(max_sum, window_sum)
```

**Keywords:** "size K", "window of K", "exactly K elements"

**Problemas (5-6):**
1. Maximum Average Subarray I (LC 643)
2. Maximum Sum of Distinct Subarrays With Length K (LC 2461)
3. Sliding Window Maximum (LC 239) - con deque
4. Find All Anagrams in String (LC 438)
5. Permutation in String (LC 567)
6. Minimum Swaps to Group All 1's Together (LC 1151)

---

### **Patrón 10: Prefix Sum + HashMap** (Días 23-25)

**Cuándo usarlo:**
- Subarrays con suma específica
- Subarrays divisibles por K
- Count de subarrays que cumplen condición

**Template:**
```python
prefix_sum = 0
count = {0: 1}  # importante inicializar
result = 0

for num in arr:
    prefix_sum += num
    if (prefix_sum - target) in count:
        result += count[prefix_sum - target]
    count[prefix_sum] = count.get(prefix_sum, 0) + 1
```

**Keywords:** "subarray sum equals", "divisible by", "count subarrays"

**Problemas (5-6):**
1. Subarray Sum Equals K (LC 560)
2. Continuous Subarray Sum (LC 523)
3. Subarray Sums Divisible by K (LC 974)
4. Make Sum Divisible by P (LC 1590)
5. Count Number of Nice Subarrays (LC 1248)
6. Binary Subarrays With Sum (LC 930)

---

### **Patrón 11: Sort + Two Pointers** (Días 26-27)

**Cuándo usarlo:**
- Ordenar primero simplifica el problema
- Buscar tripletas/cuádruplos

**Template:**
```python
arr.sort()
# luego aplicar two pointers
```

**Keywords:** "triplet", "quadruplet", "closest sum", después de mencionar sorting

**Problemas (5-6):**
1. 3Sum (LC 15)
2. 3Sum Closest (LC 16)
3. 4Sum (LC 18)
4. Valid Triangle Number (LC 611)
5. Boats to Save People (LC 881)
6. Minimize Maximum Pair Sum in Array (LC 1877)

---

### **Patrón 12: Sort + Greedy** (Días 28-29)

**Cuándo usarlo:**
- Scheduling/interval problems
- Asignación óptima
- Maximizar/minimizar con elección local

**Template:**
```python
arr.sort(key=lambda x: x[criterio])
# tomar decisiones greedy en orden
```

**Keywords:** "intervals", "meetings", "jobs", "assign", "maximize"

**Problemas (5-6):**
1. Non-overlapping Intervals (LC 435)
2. Merge Intervals (LC 56)
3. Meeting Rooms II (LC 253)
4. Minimum Number of Arrows to Burst Balloons (LC 452)
5. Assign Cookies (LC 455)
6. Jump Game II (LC 45)

---

### **Patrón 13: Modified Merge Sort (Inversions/Reverse Pairs)** (Días 30-31)

**Cuándo usarlo:**
- Contar inversiones
- Reverse pairs
- Count of smaller numbers after self

**Concepto:** Usar merge sort y contar durante el merge

**Keywords:** "inversions", "reverse pairs", "count smaller"

**Problemas (5-6):**
1. Count of Smaller Numbers After Self (LC 315)
2. Reverse Pairs (LC 493)
3. Count of Range Sum (LC 327)
4. Global and Local Inversions (LC 775)
5. Create Sorted Array Through Instructions (LC 1649)
6. Count of Smaller Number (LintCode 248)

---

### **Patrón 14: Classic Binary Search** (Días 32-33)

**Cuándo usarlo:**
- Array **ordenado**
- Buscar elemento específico

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
return -1
```

**Keywords:** "sorted", "search", "find target", O(log n)

**Problemas (5-6):**
1. Binary Search (LC 704)
2. First Bad Version (LC 278)
3. Search Insert Position (LC 35)
4. Find First and Last Position (LC 34)
5. Valid Perfect Square (LC 367)
6. Arranging Coins (LC 441)

---

### **Patrón 15: Peak Finding (Binary Search)** (Día 34)

**Cuándo usarlo:**
- Encontrar pico/valle local
- Función no estrictamente ordenada

**Template:**
```python
left, right = 0, len(arr) - 1
while left < right:
    mid = left + (right - left) // 2
    if arr[mid] < arr[mid + 1]:
        left = mid + 1  # pico está a la derecha
    else:
        right = mid
return left
```

**Keywords:** "peak", "local maximum", "mountain array"

**Problemas (5-6):**
1. Find Peak Element (LC 162)
2. Peak Index in Mountain Array (LC 852)
3. Find in Mountain Array (LC 1095)
4. Minimum in Rotated Sorted Array (LC 153)
5. Find Minimum in Rotated Sorted Array II (LC 154)
6. Single Element in Sorted Array (LC 540)

---

### **Patrón 16: Rotated Sorted Array Search** (Día 35)

**Cuándo usarlo:**
- Array ordenado pero rotado
- Buscar en array rotado

**Template:**
```python
left, right = 0, len(arr) - 1
while left <= right:
    mid = left + (right - left) // 2
    if arr[mid] == target:
        return mid
    
    # determinar qué mitad está ordenada
    if arr[left] <= arr[mid]:  # izquierda ordenada
        if arr[left] <= target < arr[mid]:
            right = mid - 1
        else:
            left = mid + 1
    else:  # derecha ordenada
        if arr[mid] < target <= arr[right]:
            left = mid + 1
        else:
            right = mid - 1
```

**Keywords:** "rotated", "sorted and rotated"

**Problemas (5-6):**
1. Search in Rotated Sorted Array (LC 33)
2. Search in Rotated Sorted Array II (LC 81)
3. Find Minimum in Rotated Sorted Array (LC 153)
4. Find Minimum in Rotated Sorted Array II (LC 154)
5. Rotate Array (LC 189) - verificación
6. Check if Array Is Sorted and Rotated (LC 1752)

---

### **Patrón 17: Binary Search on Answer** (Días 36-37)

**Cuándo usarlo:**
- Buscar el mínimo/máximo que satisface condición
- "Minimize maximum" o "Maximize minimum"
- Range de posibles respuestas

**Template:**
```python
def is_valid(mid):
    # verificar si mid es válido
    pass

left, right = min_answer, max_answer
while left < right:
    mid = left + (right - left) // 2
    if is_valid(mid):
        right = mid  # buscar respuesta menor
    else:
        left = mid + 1
return left
```

**Keywords:** "minimize maximum", "maximize minimum", "smallest sufficient", "largest possible"

**Problemas (5-6):**
1. Koko Eating Bananas (LC 875)
2. Capacity To Ship Packages Within D Days (LC 1011)
3. Minimum Number of Days to Make m Bouquets (LC 1482)
4. Magnetic Force Between Two Balls (LC 1552)
5. Split Array Largest Sum (LC 410)
6. Find K-th Smallest Pair Distance (LC 719)

---

### **Patrón 18: Matrix Traversal** (Días 38-39)

**Cuándo usarlo:**
- Recorrer matriz en orden específico
- Spiral, diagonal, zigzag

**Template (Spiral):**
```python
top, bottom = 0, len(matrix) - 1
left, right = 0, len(matrix[0]) - 1

while top <= bottom and left <= right:
    # derecha
    for i in range(left, right + 1):
        result.append(matrix[top][i])
    top += 1
    
    # abajo
    for i in range(top, bottom + 1):
        result.append(matrix[i][right])
    right -= 1
    
    # izquierda (si queda fila)
    if top <= bottom:
        for i in range(right, left - 1, -1):
            result.append(matrix[bottom][i])
        bottom -= 1
    
    # arriba (si queda columna)
    if left <= right:
        for i in range(bottom, top - 1, -1):
            result.append(matrix[i][left])
        left += 1
```

**Keywords:** "spiral", "diagonal", "traverse matrix"

**Problemas (5-6):**
1. Spiral Matrix (LC 54)
2. Spiral Matrix II (LC 59)
3. Diagonal Traverse (LC 498)
4. Matrix Diagonal Sum (LC 1572)
5. Lucky Numbers in Matrix (LC 1380)
6. Transpose Matrix (LC 867)

---

### **Patrón 19: Matrix Search** (Día 40)

**Cuándo usarlo:**
- Buscar en matriz ordenada
- Rows/columns ordenadas

**Template:**
```python
# Para matriz ordenada (row-wise y column-wise)
row, col = 0, len(matrix[0]) - 1
while row < len(matrix) and col >= 0:
    if matrix[row][col] == target:
        return True
    elif matrix[row][col] > target:
        col -= 1
    else:
        row += 1
return False
```

**Keywords:** "search matrix", "sorted rows", "sorted columns"

**Problemas (5-6):**
1. Search a 2D Matrix (LC 74)
2. Search a 2D Matrix II (LC 240)
3. Find a Peak Element II (LC 1901)
4. Kth Smallest Element in Sorted Matrix (LC 378)
5. Count Negative Numbers in Sorted Matrix (LC 1351)
6. Valid Sudoku (LC 36) - verificación

---

### **Patrón 20: Matrix Modification** (Días 41-42)

**Cuándo usarlo:**
- Modificar matriz in-place
- Set rows/columns a cero
- Rotar matriz

**Template (Set Zeroes):**
```python
# Usar primera fila/columna como marcadores
first_row_zero = any(matrix[0][j] == 0 for j in range(cols))
first_col_zero = any(matrix[i][0] == 0 for i in range(rows))

# Marcar
for i in range(1, rows):
    for j in range(1, cols):
        if matrix[i][j] == 0:
            matrix[i][0] = 0
            matrix[0][j] = 0

# Aplicar
for i in range(1, rows):
    for j in range(1, cols):
        if matrix[i][0] == 0 or matrix[0][j] == 0:
            matrix[i][j] = 0
```

**Keywords:** "in-place", "set zeroes", "rotate", "modify matrix"

**Problemas (5-6):**
1. Set Matrix Zeroes (LC 73)
2. Rotate Image (LC 48)
3. Game of Life (LC 289)
4. Toeplitz Matrix (LC 766)
5. Flood Fill (LC 733)
6. Image Smoother (LC 661)

---

### **Patrón 21: Prefix/Suffix Products** (Día 43)

**Cuándo usarlo:**
- Producto de array excepto self
- Multiplicación acumulativa

**Template:**
```python
n = len(nums)
result = [1] * n

# Prefix products
prefix = 1
for i in range(n):
    result[i] = prefix
    prefix *= nums[i]

# Suffix products
suffix = 1
for i in range(n - 1, -1, -1):
    result[i] *= suffix
    suffix *= nums[i]
```

**Keywords:** "product except self", "without division"

**Problemas (5-6):**
1. Product of Array Except Self (LC 238)
2. Maximum Product Subarray (LC 152) - combinado con Kadane
3. Maximum Product of Three Numbers (LC 628)
4. Sign of Product of Array (LC 1822)
5. Minimum Time to Make Array Sum At Most x (LC 2809)
6. Find the Original Array of Prefix Xor (LC 2433) - similar concept

---

## ✅ Checkpoint Post-Arrays (Día 44-45)

Después de dominar los 21 patrones de arrays:

### Auto-evaluación:
- [ ] ¿Puedes identificar el patrón en 2-3 minutos al leer un problema?
- [ ] ¿Has resuelto 5-6 problemas por cada patrón? (Total: ~105-126 problemas)
- [ ] ¿Puedes explicar el approach antes de codear?
- [ ] ¿Conoces la complejidad de cada patrón?

### Práctica Mixta (2-3 días):
- Resuelve 10-15 problemas de arrays **sin saber el patrón** de antemano
- Simula condiciones de entrevista
- Explica en voz alta

**Si dominas estos 21 patrones, ya estás interview-ready para la mayoría de empresas que hacen ~70% arrays en sus entrevistas.**

---

## 🔄 FASE 2: STRINGS (Semanas 9-11)

### Patrones de Strings (muchos reusan conceptos de arrays):

1. **Character Counting (HashMap)** - similar a array patrón 6
   - Valid Anagram, First Unique Character
   
2. **Two Pointers en Strings** - similar a array patrón 2-3
   - Valid Palindrome, Reverse String
   
3. **Sliding Window en Strings** - similar a array patrón 8-9
   - Longest Substring Without Repeating Characters
   
4. **String Matching (KMP/Rabin-Karp)** - nuevo
   - Implement strStr(), Repeated Substring Pattern
   
5. **Parentheses/Brackets (Stack)** - nuevo
   - Valid Parentheses, Generate Parentheses

**Resolver 5-6 problemas por patrón = ~25-30 problemas**

---

## 🔗 FASE 3: LINKED LISTS (Semanas 12-13)

### Patrones de Linked Lists:

1. **Fast-Slow Pointers** - similar a arrays
   - Linked List Cycle, Middle of Linked List
   
2. **Reverse Linked List** - nuevo
   - Reverse Linked List, Reverse Nodes in k-Group
   
3. **Merge Lists** - nuevo
   - Merge Two Sorted Lists, Merge k Sorted Lists
   
4. **Remove/Insert Nodes** - nuevo
   - Remove Nth Node From End, Delete Node
   
5. **Dummy Node Technique** - nuevo
   - Add Two Numbers, Partition List

**Resolver 5-6 problemas por patrón = ~25-30 problemas**

---

## 📚 FASE 4: STACKS & QUEUES (Semanas 14-15)

### Patrones:

1. **Monotonic Stack** - nuevo
   - Next Greater Element, Daily Temperatures
   
2. **Stack for Validation** - nuevo
   - Valid Parentheses, Min Stack
   
3. **Queue for BFS** - será importante para trees/graphs
   - Implement Queue using Stacks

**Resolver 5-6 problemas por patrón = ~15-18 problemas**

---

## 🌳 FASE 5: TREES (Semanas 16-19)

### Patrones:

1. **DFS - Preorder/Inorder/Postorder** - nuevo
2. **BFS - Level Order** - nuevo
3. **BST Properties** - nuevo
4. **Path Problems** - nuevo
5. **Tree Construction** - nuevo

**Resolver 5-6 problemas por patrón = ~25-30 problemas**

---

## 🗺️ FASE 6: GRAPHS (Semanas 20-22)

### Patrones:

1. **DFS en Graphs** - similar a trees
2. **BFS en Graphs** - similar a trees
3. **Union Find** - nuevo
4. **Topological Sort** - nuevo

**Resolver 5-6 problemas por patrón = ~20-24 problemas**

---

## 🚀 FASE 7: AVANZADO (Semanas 23-24)

### Estructuras opcionales:

1. **Heaps/Priority Queue**
2. **Tries**
3. **Segment Trees** (raro en entrevistas)

**Solo si tienes tiempo o empresa específica lo requiere.**

---

## 📊 Resumen de Números

### Total de Problemas por Fase:
- **Arrays:** 105-126 problemas (21 patrones × 5-6)
- **Strings:** 25-30 problemas
- **Linked Lists:** 25-30 problemas
- **Stacks/Queues:** 15-18 problemas
- **Trees:** 25-30 problemas
- **Graphs:** 20-24 problemas

**TOTAL:** ~215-258 problemas en 22-24 semanas

### Pero lo más importante:
**Después de completar solo ARRAYS (105-126 problemas en 8 semanas), ya estarás interview-ready para muchas posiciones.**

---

## 🎯 Estrategia de Reconocimiento de Patrones

### Cómo identificar el patrón por keywords:

| Keyword/Constraint | Patrón Probable |
|-------------------|-----------------|
| "sorted array" | Binary Search, Two Pointers (opposite) |
| "in-place", "without extra space" | Two Pointers (same direction) |
| "longest substring/subarray" | Sliding Window (variable) |
| "size K", "window of K" | Sliding Window (fixed) |
| "sum equals K", "divisible by" | Prefix Sum + HashMap |
| "duplicates", "unique" | HashSet |
| "frequency", "count", "anagram" | HashMap |
| "maximum subarray sum" | Kadane's Algorithm |
| "rotate", "shift" | Array Rotation |
| "intervals", "meetings" | Sort + Greedy |
| "minimize maximum", "maximize minimum" | Binary Search on Answer |
| "spiral", "diagonal" | Matrix Traversal |
| "peak", "local maximum" | Peak Finding (BS) |
| "rotated sorted array" | Rotated Array Search |
| "inversions", "reverse pairs" | Modified Merge Sort |
| "product except self" | Prefix/Suffix Products |

---

## 💡 Tips para Maximizar Aprendizaje

### 1. Usa IA como Tutor Personal
- ChatGPT, Claude, Gemini son excelentes para:
  - Explicar conceptos rápidamente
  - Revisar tu código
  - Sugerir optimizaciones
  - Generar problemas similares

**Ejemplo de prompt:**
> "Explícame por qué usar sliding window es mejor que nested loops para 'longest substring without repeating characters'. Dame la intuición, no solo el código."

### 2. Template-Based Learning
- Después de resolver 5-6 problemas de un patrón, **crea tu propio template**
- Memoriza el template, no las soluciones individuales
- Personaliza el template con tus propios comentarios

### 3. Keyword Recognition Practice
- Mantén una lista de keywords → patrón
- Antes de resolver un problema, identifica 2-3 keywords
- Practica decir en voz alta: "Veo 'sorted array' y 'pair sum', esto es Two Pointers opposite direction"

### 4. Spaced Repetition
- Después de dominar un patrón, revísalo cada:
  - 3 días
  - 1 semana
  - 2 semanas
  - 1 mes

### 5. Calidad > Cantidad
- No te apresures a completar los 21 patrones de arrays
- Mejor: dominar perfectamente 10 patrones que resolver superficialmente 21

### 6. Diario de Patrones
Mantén un documento con:
```
Patrón: Sliding Window Variable
Keywords: "longest", "minimum", "at most K"
Template: [tu código]
Problemas resueltos: [lista]
Errores comunes: [tus errores]
```

---

## ⏱️ Cronograma Diario Recomendado

### Días 1-43 (Fase Arrays):
- **30 min:** Revisar el patrón del día (leer teoría, template)
- **60-90 min:** Resolver 1 problema nuevo
  - 10 min: Leer y entender el problema
  - 5 min: Identificar patrón y diseñar approach
  - 30-40 min: Implementar solución
  - 15 min: Revisar soluciones optimales
- **20-30 min:** Resolver 1 problema de patrón anterior (review)

**Total: 2-2.5 horas/día**

### Días posteriores (otras estructuras):
- **Similar enfoque**, pero puedes acelerar si reconoces patrones transferibles

---

## 🎓 Milestone Checklist

### Después de Arrays (Semana 8):
- [ ] Dominé 21 patrones
- [ ] Resolví 105+ problemas
- [ ] Puedo identificar el patrón en 2-3 min
- [ ] Tengo mis propios templates
- [ ] Puedo hacer mock interviews de array problems

### Después de Strings + Linked Lists (Semana 13):
- [ ] +50 problemas más (total ~155)
- [ ] Veo cómo patrones se transfieren entre estructuras

### Después de Trees + Graphs (Semana 22):
- [ ] +50 problemas más (total ~205)
- [ ] Domino BFS/DFS en diferentes contextos
- [ ] Listo para entrevistas en FAANG

---

## 🔥 Por Qué Este Enfoque Funciona

### 1. **Dominio Profundo vs Exposición Superficial**
- Resolver 126 problemas de arrays (con 21 patrones) vs 126 problemas random
- Cuando ves un nuevo array problem, **instantáneamente** reconoces el patrón

### 2. **Transferencia de Conocimiento**
- Many string patterns = array patterns aplicados a strings
- Fast-slow pointers: arrays → linked lists
- BFS: trees → graphs → matrix

### 3. **Confianza en Entrevistas**
- "He resuelto 120 array problems" suena amateur
- "He dominado los 21 patrones fundamentales de arrays resolviendo 6 problemas por patrón" suena experto

### 4. **Reduce Parálisis por Análisis**
- No saltas entre estructuras preguntándote "¿debería aprender trees o graphs?"
- Finish what you start: Arrays → 100% → Next

---

## 📚 Recursos por Estructura

### Para Arrays:
- **LeetCode:** Etiqueta "Array"
- **NeetCode:** Arrays & Hashing section
- **AlgoMonster:** Array patterns

### Para el resto:
- Similar: busca por estructura específica en plataformas

### IA como Co-pilot:
```
Prompt: "Dame 5 problemas de LeetCode que usen el patrón 
'sliding window variable' en arrays, ordenados por dificultad"
```

---

## 🚀 Plan de Acción Inmediato

### Esta Semana (Días 1-7):
**Meta:** Dominar los primeros 3 patrones de arrays

**Día 1-2:** Simple Traversal
- Resuelve: Running Sum, Find Even Digits, Richest Customer, Count Positive/Negative, Average Salary

**Día 3-5:** Two Pointers (Opposite)
- Resuelve: Two Sum II, Container With Water, Valid Palindrome, 3Sum

**Día 6-7:** Two Pointers (Same Direction)
- Resuelve: Remove Duplicates, Move Zeroes, Remove Element

**Resultado:** 15 problemas, 3 patrones dominados

---

## 🏆 Mentalidad de Éxito

### "DSA no es difícil. Depende de qué tan emocionado estés por aprenderlo."

**Reframe mental:**
- ❌ "Tengo que resolver 500 problemas para conseguir trabajo"
- ✅ "Voy a dominar 21 patrones de arrays en 8 semanas y seré imparable"

**Celebrate small wins:**
- Cada patrón dominado = 🎉
- Cada 25 problemas = 🏅
- Cada estructura completa = 🏆

---

## 💪 Conclusión

### Este plan es diferente porque:
1. **No dispersa tu atención** - Una estructura a la vez
2. **Profundidad sobre amplitud** - 5-6 problemas por patrón
3. **Transferencia inteligente** - Patrones se reciclan entre estructuras
4. **Interview-ready en 8 semanas** - Solo con arrays
5. **IA-powered** - Usa tecnología para aprender más rápido

### Siguiente paso:
**Empieza AHORA. Abre LeetCode. Resuelve "Running Sum of 1D Array".**

No esperes al lunes. No esperes a "estar listo". El mejor momento para empezar fue ayer. El segundo mejor momento es ahora.

---

**¡Éxito en tu journey! 🚀 Recuerda: Patrones > Problemas.**