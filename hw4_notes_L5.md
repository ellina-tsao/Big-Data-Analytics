# **Swirl R Programming 學習筆記**
### **Lesson 5: Missing Values**

---

### **1. NA 在 R 中的意義**
- **`NA` (Not Available)** 表示**缺失數據**，在統計分析時，不能忽略這些遺漏值。
- **任何涉及 `NA` 的運算都會產生 `NA`**：
  ```r
  x <- c(44, NA, 5, NA)
  x * 3  # 會產生 NA
  ```
  - 輸出：`[1] 132  NA  15  NA`

---

### **2. 隨機生成數據並檢查 NA**
- **建立包含 `NA` 的數據集**：
  ```r
  y <- rnorm(1000)      # 產生 1000 個標準常態分布的隨機數
  z <- rep(NA, 1000)    # 產生 1000 個 NA
  my_data <- sample(c(y, z), 100)  # 從 y 和 z 中隨機抽取 100 個值
  ```

- **使用 `is.na()` 檢查哪些元素是 `NA`**：
  ```r
  my_na <- is.na(my_data)  # 產生布林向量，表示哪些值為 NA
  ```

- **查看 `my_na`**：
  ```r
  print(my_na)  # 顯示哪些位置是 NA
  ```

---

### **3. 計算 NA 的數量**
- **`NA` 無法直接比較**：
  ```r
  my_data == NA  # 錯誤的用法，會得到一個全為 NA 的向量
  ```
  
- **計算 `NA` 的數量**：
  ```r
  sum(my_na)  # 計算 `my_na` 中的 TRUE (即 `NA` 的數量)
  ```
  - R 將 `TRUE` 視為 `1`，`FALSE` 視為 `0`，所以 `sum()` 可用來計算 `NA` 數量。

---

### **4. NaN (Not a Number)**
- **`NaN` 代表非數值 (Not a Number)**：
  ```r
  0 / 0  # 產生 NaN
  ```
  - 輸出：`[1] NaN`
  
- **`Inf` (無限大) 也可能產生 `NaN`**：
  ```r
  Inf - Inf  # 產生 NaN
  ```
  - 輸出：`[1] NaN`

---

### **5. 課程重點**
✔ `NA` 代表缺失數據，無法直接運算或比較。  
✔ `is.na(x)` 可用來檢查 `NA`，`sum(is.na(x))` 可計算 `NA` 的數量。  
✔ `NaN` (Not a Number) 通常由 `0/0` 或 `Inf - Inf` 產生。  
✔ **小心 `NA` 影響計算結果**，務必在分析前處理遺漏值。  
