# Plan Express: Big 6 Patrones Más Frecuentes

## 🎯 Objetivo: Interview-Ready en 30 Días

Este plan te prepara para **70% de entrevistas técnicas** enfocándote exclusivamente en los 6 patrones que aparecen con mayor frecuencia según análisis de 500+ problemas.

**Resultado esperado:** 36-42 problemas dominados + capacidad de resolver 60-70% de problemas Medium en entrevistas.

---

## 📊 Los Big 6 Patrones

| Patrón | Frecuencia en Entrevistas | Problemas a Resolver |
|--------|--------------------------|---------------------|
| 1. Two Pointers | 25-30% | 6-8 problemas |
| 2. Sliding Window | 20-25% | 6-8 problemas |
| 3. HashMap/HashSet | 30-35% | 6-8 problemas |
| 4. Binary Search | 15-20% | 6 problemas |
| 5. Fast & Slow Pointers | 10-15% | 6 problemas |
| 6. Prefix Sum | 10-12% | 6 problemas |

**Total:** 36-44 problemas en 30 días = ~1-2 problemas/día

---

## 🗓️ SEMANA 1: Two Pointers + HashMap/HashSet

### **Día 1-3: Two Pointers (Opposite Direction)**

#### Concepto:
Dos punteros que se mueven desde extremos opuestos del array. Usado en arrays **ordenados**.

#### Template:
```python
def two_pointers_opposite(arr, target):
    left, right = 0, len(arr) - 1
    
    while left < right:
        current_sum = arr[left] + arr[right]
        
        if current_sum == target:
            return [left, right]
        elif current_sum < target:
            left += 1
        else:
            right -= 1
    
    return [-1, -1]
```

#### Keywords: 
"sorted array", "pair sum", "two elements", "target sum"

#### Problemas LeetCode/NeetCode:

| # | Problema | Dificultad | LeetCode # | NeetCode Link |
|---|----------|-----------|-----------|---------------|
| 1 | **Two Sum II - Input Array Is Sorted** | Easy | LC 167 | [Link](https://neetcode.io/problems/two-integer-sum-ii) |
| 2 | **Valid Palindrome** | Easy | LC 125 | [Link](https://neetcode.io/problems/is-palindrome) |
| 3 | **3Sum** | Medium | LC 15 | [Link](https://neetcode.io/problems/three-integer-sum) |
| 4 | **Container With Most Water** | Medium | LC 11 | [Link](https://neetcode.io/problems/max-water-container) |
| 5 | **Trapping Rain Water** ⭐ | Hard | LC 42 | [Link](https://neetcode.io/problems/trapping-rain-water) |
| 6 | **3Sum Closest** | Medium | LC 16 | - |

**Meta Día 3:** Dominar el template, resolver 5-6 problemas

---

### **Día 4-6: HashMap/HashSet (Counting & Existence)**

#### Concepto:
Usar HashMap para contar frecuencias o HashSet para verificar existencia en O(1).

#### Template HashMap (Counting):
```python
from collections import Counter

def frequency_pattern(arr):
    freq = Counter(arr)
    # o manualmente:
    freq = {}
    for num in arr:
        freq[num] = freq.get(num, 0) + 1
    
    # usar freq para resolver problema
    return result
```

#### Template HashSet (Existence):
```python
def existence_pattern(arr):
    seen = set()
    
    for num in arr:
        if num in seen:
            return True  # duplicado encontrado
        seen.add(num)
    
    return False
```

#### Keywords:
"frequency", "count", "duplicate", "unique", "anagram", "contains"

#### Problemas LeetCode/NeetCode:

| # | Problema | Dificultad | LeetCode # | NeetCode Link |
|---|----------|-----------|-----------|---------------|
| 1 | **Two Sum** ⭐ | Easy | LC 1 | [Link](https://neetcode.io/problems/two-integer-sum) |
| 2 | **Contains Duplicate** | Easy | LC 217 | [Link](https://neetcode.io/problems/duplicate-integer) |
| 3 | **Valid Anagram** | Easy | LC 242 | [Link](https://neetcode.io/problems/is-anagram) |
| 4 | **Group Anagrams** | Medium | LC 49 | [Link](https://neetcode.io/problems/anagram-groups) |
| 5 | **Top K Frequent Elements** | Medium | LC 347 | [Link](https://neetcode.io/problems/top-k-elements-in-list) |
| 6 | **Longest Consecutive Sequence** ⭐ | Medium | LC 128 | [Link](https://neetcode.io/problems/longest-consecutive-sequence) |
| 7 | **Encode and Decode Strings** | Medium | LC 271 | [Link](https://neetcode.io/problems/string-encode-and-decode) |

**Meta Día 6:** Entender cuándo usar HashMap vs HashSet, resolver 6-7 problemas

---

### **Día 7: Repaso Semana 1**
- Resolver 2-3 problemas mixtos sin saber el patrón
- Practicar explicar el approach en voz alta
- Crear tus propios templates personalizados

---

## 🗓️ SEMANA 2: Sliding Window + Fast & Slow Pointers

### **Día 8-11: Sliding Window (Variable & Fixed)**

#### Concepto:
Ventana dinámica sobre subarray/substring contiguo. **Evolución de Two Pointers**.

#### Template Variable Size:
```python
def sliding_window_variable(arr):
    left = 0
    max_length = 0
    window_data = {}  # o set(), o contador
    
    for right in range(len(arr)):
        # Agregar arr[right] a la ventana
        window_data[arr[right]] = window_data.get(arr[right], 0) + 1
        
        # Mientras la ventana sea inválida, reducirla
        while ventana_invalida(window_data):
            window_data[arr[left]] -= 1
            if window_data[arr[left]] == 0:
                del window_data[arr[left]]
            left += 1
        
        # Actualizar resultado con ventana válida
        max_length = max(max_length, right - left + 1)
    
    return max_length
```

#### Template Fixed Size:
```python
def sliding_window_fixed(arr, k):
    window_sum = sum(arr[:k])
    max_sum = window_sum
    
    for i in range(k, len(arr)):
        window_sum += arr[i] - arr[i - k]
        max_sum = max(max_sum, window_sum)
    
    return max_sum
```

#### Keywords:
"longest substring", "shortest subarray", "at most K", "window size K", "contiguous"

#### Problemas LeetCode/NeetCode:

| # | Problema | Dificultad | LeetCode # | NeetCode Link |
|---|----------|-----------|-----------|---------------|
| 1 | **Best Time to Buy and Sell Stock** | Easy | LC 121 | [Link](https://neetcode.io/problems/buy-and-sell-crypto) |
| 2 | **Longest Substring Without Repeating Chars** ⭐ | Medium | LC 3 | [Link](https://neetcode.io/problems/longest-substring-without-duplicates) |
| 3 | **Longest Repeating Character Replacement** ⭐ | Medium | LC 424 | [Link](https://neetcode.io/problems/longest-repeating-substring-with-replacement) |
| 4 | **Permutation in String** | Medium | LC 567 | [Link](https://neetcode.io/problems/permutation-string) |
| 5 | **Minimum Window Substring** ⭐ | Hard | LC 76 | [Link](https://neetcode.io/problems/minimum-window-with-characters) |
| 6 | **Sliding Window Maximum** | Hard | LC 239 | [Link](https://neetcode.io/problems/sliding-window-maximum) |
| 7 | **Max Consecutive Ones III** | Medium | LC 1004 | - |
| 8 | **Minimum Size Subarray Sum** | Medium | LC 209 | - |

**Meta Día 11:** Distinguir cuándo usar variable vs fixed, resolver 6-8 problemas

---

### **Día 12-14: Fast & Slow Pointers**

#### Concepto:
Dos punteros que avanzan a diferentes velocidades. Usado principalmente en **Linked Lists** pero también en arrays.

#### Template:
```python
def fast_slow_pointers(head):
    slow = fast = head
    
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        
        if slow == fast:
            return True  # ciclo detectado
    
    return False
```

#### Keywords:
"cycle", "middle element", "duplicate number", "in-place", "linked list"

#### Problemas LeetCode/NeetCode:

| # | Problema | Dificultad | LeetCode # | NeetCode Link |
|---|----------|-----------|-----------|---------------|
| 1 | **Linked List Cycle** ⭐ | Easy | LC 141 | [Link](https://neetcode.io/problems/linked-list-cycle-detection) |
| 2 | **Middle of the Linked List** | Easy | LC 876 | - |
| 3 | **Happy Number** | Easy | LC 202 | - |
| 4 | **Find the Duplicate Number** | Medium | LC 287 | [Link](https://neetcode.io/problems/find-duplicate-integer) |
| 5 | **Linked List Cycle II** | Medium | LC 142 | - |
| 6 | **Palindrome Linked List** | Easy | LC 234 | - |

**Meta Día 14:** Entender el concepto de "tortuga y liebre", resolver 6 problemas

---

### **Día 15: Repaso Semana 2**
- Resolver 3 problemas mixtos (Sliding Window + Fast-Slow)
- Comparar: ¿Cuándo usar Sliding Window vs Two Pointers?

---

## 🗓️ SEMANA 3: Binary Search

### **Día 16-21: Binary Search (Classic + Variantes)**

#### Concepto:
Búsqueda logarítmica en arrays ordenados o funciones monótonas. **El patrón más versátil.**

#### Template Classic:
```python
def binary_search(arr, target):
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

#### Template: Binary Search on Answer
```python
def binary_search_answer(arr, condition):
    def is_valid(mid):
        # Verificar si mid satisface la condición
        return True/False
    
    left, right = min_answer, max_answer
    
    while left < right:
        mid = left + (right - left) // 2
        
        if is_valid(mid):
            right = mid  # buscar menor válido
        else:
            left = mid + 1
    
    return left
```

#### Keywords:
"sorted", "search", "find target", "O(log n)", "rotated", "minimum/maximum that satisfies"

#### Problemas LeetCode/NeetCode:

**Día 16-17: Classic Binary Search**

| # | Problema | Dificultad | LeetCode # | NeetCode Link |
|---|----------|-----------|-----------|---------------|
| 1 | **Binary Search** | Easy | LC 704 | [Link](https://neetcode.io/problems/binary-search) |
| 2 | **Search a 2D Matrix** | Medium | LC 74 | [Link](https://neetcode.io/problems/search-2d-matrix) |

**Día 18-19: Rotated Sorted Array**

| # | Problema | Dificultad | LeetCode # | NeetCode Link |
|---|----------|-----------|-----------|---------------|
| 3 | **Search in Rotated Sorted Array** ⭐ | Medium | LC 33 | [Link](https://neetcode.io/problems/search-rotated-sorted-array) |
| 4 | **Find Minimum in Rotated Sorted Array** | Medium | LC 153 | [Link](https://neetcode.io/problems/find-minimum-in-rotated-sorted-array) |

**Día 20-21: Binary Search on Answer**

| # | Problema | Dificultad | LeetCode # | NeetCode Link |
|---|----------|-----------|-----------|---------------|
| 5 | **Koko Eating Bananas** ⭐ | Medium | LC 875 | [Link](https://neetcode.io/problems/eating-bananas) |
| 6 | **Find First and Last Position** | Medium | LC 34 | - |
| 7 | **Time Based Key-Value Store** | Medium | LC 981 | [Link](https://neetcode.io/problems/time-based-key-value-store) |

**Meta Día 21:** Dominar las 3 variantes de Binary Search, resolver 6-7 problemas

---

### **Día 22: Repaso Semana 3**
- Resolver 2-3 problemas de Binary Search avanzado
- Practicar: "¿Esto es monotónico? ¿Puedo usar BS?"

---

## 🗓️ SEMANA 4: Prefix Sum + Integración

### **Día 23-26: Prefix Sum + HashMap**

#### Concepto:
Precálculo de sumas acumulativas + HashMap para encontrar subarrays que cumplan condición.

#### Template:
```python
def prefix_sum_hashmap(arr, target):
    prefix_sum = 0
    count = {0: 1}  # Importante: suma 0 existe antes de empezar
    result = 0
    
    for num in arr:
        prefix_sum += num
        
        # ¿Existe un prefix que nos dé el target?
        if (prefix_sum - target) in count:
            result += count[prefix_sum - target]
        
        # Agregar prefix actual al mapa
        count[prefix_sum] = count.get(prefix_sum, 0) + 1
    
    return result
```

#### Keywords:
"subarray sum equals", "divisible by K", "count subarrays", "continuous subarray"

#### Problemas LeetCode/NeetCode:

| # | Problema | Dificultad | LeetCode # | NeetCode Link |
|---|----------|-----------|-----------|---------------|
| 1 | **Running Sum of 1d Array** | Easy | LC 1480 | - |
| 2 | **Subarray Sum Equals K** ⭐ | Medium | LC 560 | - |
| 3 | **Continuous Subarray Sum** | Medium | LC 523 | - |
| 4 | **Product of Array Except Self** | Medium | LC 238 | [Link](https://neetcode.io/problems/products-of-array-discluding-self) |
| 5 | **Maximum Subarray** (Kadane's) ⭐ | Medium | LC 53 | [Link](https://neetcode.io/problems/maximum-subarray) |
| 6 | **Range Sum Query - Immutable** | Easy | LC 303 | - |

**Meta Día 26:** Entender el truco del prefix sum, resolver 6 problemas

---

### **Día 27-29: Práctica Mixta (Integración Big 6)**

#### Objetivo:
Resolver problemas **sin saber de antemano qué patrón usar**. Simular entrevista real.

#### Estrategia:
1. Lee el problema
2. Identifica keywords
3. Decide el patrón en 2-3 minutos
4. Implementa

#### Problemas Mixtos (Big 6 combinados):

| # | Problema | Patrón(es) | Dificultad | LeetCode # |
|---|----------|-----------|-----------|-----------|
| 1 | **Maximum Product Subarray** | Kadane's (Prefix) | Medium | LC 152 |
| 2 | **4Sum** | Two Pointers + HashMap | Medium | LC 18 |
| 3 | **Fruit Into Baskets** | Sliding Window | Medium | LC 904 |
| 4 | **Find K Closest Elements** | Binary Search + Two Pointers | Medium | LC 658 |
| 5 | **Reorder List** | Fast-Slow + Reverse | Medium | LC 143 |
| 6 | **Valid Parentheses** | HashMap (matching) | Easy | LC 20 |
| 7 | **Move Zeroes** | Two Pointers (same) | Easy | LC 283 |
| 8 | **Sort Colors** | Two Pointers | Medium | LC 75 |

**Meta Día 29:** Identificar correctamente el patrón en 80%+ de los problemas

---

### **Día 30: Mock Interview**

#### Formato:
- 2 problemas Medium (45 min cada uno)
- Explicar approach en voz alta ANTES de codear
- Analizar complejidad temporal/espacial
- Optimizar si es posible

#### Problemas Sugeridos:
1. **3Sum Closest** (LC 16) - Two Pointers
2. **Minimum Window Substring** (LC 76) - Sliding Window + HashMap

#### Plataformas para Mock Interview:
- **Pramp** (gratis, peer-to-peer)
- **interviewing.io** (con ingenieros reales)
- **NeetCode** (practice mode)

---

## 📊 Resumen de Problemas por Patrón

| Patrón | Problemas Resueltos | Core Problems Marcados ⭐ |
|--------|---------------------|-------------------------|
| 1. Two Pointers | 6-8 | Two Sum II, 3Sum, Trapping Rain Water |
| 2. HashMap/HashSet | 7 | Two Sum, Longest Consecutive Sequence |
| 3. Sliding Window | 6-8 | Longest Substring, Min Window, Character Replacement |
| 4. Fast & Slow | 6 | Linked List Cycle, Find Duplicate |
| 5. Binary Search | 6-7 | Search Rotated, Koko Bananas |
| 6. Prefix Sum | 6 | Subarray Sum K, Maximum Subarray |

**Total:** 37-42 problemas + 8 problemas mixtos = **45-50 problemas en 30 días**

---

## 🎯 Tabla de Keywords para Reconocimiento Rápido

| Si ves... | Piensa en... | Ejemplo |
|-----------|--------------|---------|
| "sorted array" + "pair/triplet" | Two Pointers (opposite) | 3Sum |
| "in-place" / "without extra space" | Two Pointers (same) | Move Zeroes |
| "longest substring/subarray" | Sliding Window (variable) | Longest Substring |
| "size K" / "window of K" | Sliding Window (fixed) | Max Average Subarray |
| "frequency" / "anagram" | HashMap (counting) | Valid Anagram |
| "contains" / "duplicate" | HashSet | Contains Duplicate |
| "cycle" / "middle" / "linked list" | Fast & Slow | Linked List Cycle |
| "sorted" + "search" + "O(log n)" | Binary Search (classic) | Binary Search |
| "rotated sorted array" | Binary Search (variant) | Search Rotated |
| "minimize maximum" / "maximize minimum" | Binary Search on Answer | Koko Bananas |
| "subarray sum equals K" | Prefix Sum + HashMap | Subarray Sum K |
| "maximum subarray sum" | Kadane's (Prefix variant) | Maximum Subarray |

---

## 💡 Recursos y Links Organizados

### **NeetCode.io** (Recomendado - Problemas Organizados por Patrón)
- **Arrays & Hashing:** https://neetcode.io/roadmap
- **Two Pointers:** https://neetcode.io/roadmap (sección Two Pointers)
- **Sliding Window:** https://neetcode.io/roadmap (sección Sliding Window)
- **Binary Search:** https://neetcode.io/roadmap (sección Binary Search)
- **Linked List:** https://neetcode.io/roadmap (Fast & Slow Pointers)

### **LeetCode - Listas Curadas**
- **Blind 75:** https://leetcode.com/discuss/general-discussion/460599/blind-75-leetcode-questions
- **NeetCode 150:** https://neetcode.io/practice
- **Grind 75:** https://www.techinterviewhandbook.org/grind75

### **Videos Explicativos (NeetCode YouTube)**
- Cada problema del plan tiene video explicativo en: https://www.youtube.com/@NeetCode
- Busca por número de LeetCode (ej: "LC 3 NeetCode")

---

## 🚀 Estrategia de Ejecución

### **Rutina Diaria (1.5-2 horas):**

**Días de Aprendizaje (Día 1-26):**
- **20 min:** Estudiar el patrón del día (template + teoría)
- **60 min:** Resolver 1-2 problemas nuevos
  - 10 min: Leer problema y identificar patrón
  - 30-40 min: Implementar solución
  - 10-20 min: Ver solución óptima y comparar
- **20-30 min:** Revisar 1 problema anterior (spaced repetition)

**Días de Práctica Mixta (Día 27-29):**
- **90 min:** Resolver 2 problemas sin hints
- **30 min:** Analizar soluciones y crear comparaciones

**Día de Mock Interview (Día 30):**
- **90 min:** Simular condiciones reales de entrevista

---

## ✅ Checklist de Dominio por Patrón

### Two Pointers ✓
- [ ] Puedo identificar cuándo usar opposite vs same direction
- [ ] Sé manejar el caso de arrays ordenados vs no ordenados
- [ ] Entiendo cómo evitar duplicados en 3Sum
- [ ] Puedo explicar por qué es O(n) en tiempo

### HashMap/HashSet ✓
- [ ] Sé cuándo usar HashMap vs HashSet
- [ ] Puedo implementar Counter manualmente
- [ ] Entiendo el tradeoff: O(n) espacio por O(1) lookup
- [ ] Reconozco problemas de "existencia" vs "frecuencia"

### Sliding Window ✓
- [ ] Distingo entre fixed vs variable size window
- [ ] Sé cuándo expandir y cuándo contraer la ventana
- [ ] Puedo combinar Sliding Window con HashMap
- [ ] Entiendo por qué mejora nested loops (O(n²) → O(n))

### Fast & Slow Pointers ✓
- [ ] Puedo detectar ciclos con este patrón
- [ ] Sé encontrar el punto medio de una lista
- [ ] Entiendo el concepto de "tortuga y liebre"
- [ ] Puedo aplicarlo en arrays (Find Duplicate Number)

### Binary Search ✓
- [ ] Domino el template clásico (evitar infinite loops)
- [ ] Sé buscar en rotated sorted arrays
- [ ] Puedo hacer "binary search on answer"
- [ ] Reconozco funciones monótonas aunque no sean arrays

### Prefix Sum ✓
- [ ] Entiendo el truco de `{0: 1}` al inicio
- [ ] Puedo usar prefix sum para subarray problems
- [ ] Sé combinar con HashMap para O(n) solutions
- [ ] Reconozco cuándo Kadane's es mejor opción

---

## 🏆 Milestone Final (Día 30)

### Auto-Evaluación:
- [ ] Resolví 45-50 problemas en total
- [ ] Domino los 6 patrones más frecuentes
- [ ] Puedo identificar el patrón correcto en 2-3 min
- [ ] Explico mi approach antes de codear
- [ ] Conozco la complejidad de cada solución
- [ ] He hecho al menos 1 mock interview completa

### ¿Qué sigue después del Día 30?

**Opción A: Reforzar con más problemas (Semanas 5-6)**
- Resolver otros 20-30 problemas de los Big 6
- Enfocarte en problemas Hard de estos patrones

**Opción B: Expandir a otros patrones (Semanas 5-8)**
- Agregar: DFS/BFS, Backtracking, Dynamic Programming
- Seguir el plan completo de 21 patrones de arrays

**Opción C: Empezar a aplicar a trabajos**
- Con los Big 6 dominados, ya puedes pasar el 70% de entrevistas
- Continúa practicando mientras aplicas

---

## 💪 Mensaje Final

### "Los Big 6 son tu arma secreta"

**No necesitas 500 problemas. No necesitas 6 meses.**

Con **30 días** de práctica enfocada en los patrones MÁS frecuentes:
- ✅ Pasarás screening de la mayoría de empresas
- ✅ Tendrás confianza en entrevistas
- ✅ Sabrás exactamente qué hacer cuando veas un problema

**La clave:** Profundidad > Amplitud

Mejor dominar 6 patrones (45 problemas) que tocar superficialmente 15 patrones (150 problemas).

---

**¡Empieza HOY! Día 1, Problema 1: Two Sum II (LC 167)**

No esperes. No procrastines. Abre LeetCode ahora mismo.

🚀 **El journey de 1000 millas empieza con un solo paso.**