---

# **Swirl R Programming 學習筆記**

---

### **Lesson 1: Basic Building Blocks**

涵蓋 R 語言的基本概念，包括變數指派、向量操作、基本數學運算、快捷鍵等。


#### **1 R 作為計算機**
- 直接輸入數學運算，例如：
  ```r
  5 + 7  # 結果: 12
  ```

#### **2 變數指派**
- 使用 `<-` 來賦值：
  ```r
  x <- 5 + 7  # x 變數儲存 12
  y <- x - 3  # y 變數儲存 9
  ```

#### **3 向量 (Vectors)**
- 建立向量：
  ```r
  z <- c(1.1, 9, 3.14)  # c() 用來建立向量
  ```
- 向量運算：
  ```r
  z * 2 + 100  # 所有元素各自乘 2 再加 100
  ```

#### **4 基礎數學運算**
- 平方 (`^`) 和平方根 (`sqrt()`):
  ```r
  my_sqrt <- sqrt(z - 1)  # 計算 z 中每個元素減 1 後的平方根
  ```

#### **5 運算與變數**
- 向量除法：
  ```r
  my_div <- z / my_sqrt  # 每個元素分別相除
  ```

#### **6 向量回收**
- 短向量會重複填補：
  ```r
  c(1, 2, 3, 4) + c(0, 10)  # 短向量自動重複
  ```

#### **7 快捷鍵**
- 上鍵 (`↑`) 可回溯輸入的指令並編輯
- `Tab` 鍵可自動補全變數名稱
---

### **Lesson 2: Workspace and Files**

---

### **1. 環境與工作目錄**
- **檢查目前的工作目錄**：
  ```r
  getwd()  # 顯示目前的工作目錄
  ```
  - 例如：`[1] "/Users/ellina_tsao/NTHU/Big Data Analytics"`

- **列出目前工作目錄中的物件 (變數)**：
  ```r
  ls()  # 顯示目前環境中的變數
  ```
  - 例如：`[1] "my_div"  "my_sqrt" "x"  "y"  "z"`

- **列出目前資料夾內的檔案**：
  ```r
  list.files()  # 顯示目前資料夾內的所有檔案
  dir()         # list.files() 的別名
  ```

---

### **2. 變數與目錄操作**
- **儲存目前的工作目錄**：
  ```r
  old.dir <- getwd()  # 儲存當前的工作目錄
  ```

- **建立新資料夾**：
  ```r
  dir.create("testdir")  # 建立名為 "testdir" 的資料夾
  ```

- **切換工作目錄**：
  ```r
  setwd("testdir")  # 將工作目錄切換到 "testdir"
  ```

---

### **3. 檔案操作**
- **建立新檔案**：
  ```r
  file.create("mytest.R")  # 建立 mytest.R 檔案
  ```

- **檢查檔案是否存在**：
  ```r
  file.exists("mytest.R")  # 檢查 mytest.R 是否存在
  ```

- **查看檔案資訊**：
  ```r
  file.info("mytest.R")  # 顯示 mytest.R 的詳細資訊
  ```

- **重新命名檔案**：
  ```r
  file.rename("mytest.R", "mytest2.R")  # 將 mytest.R 重新命名為 mytest2.R
  ```

- **複製檔案**：
  ```r
  file.copy("mytest2.R", "mytest3.R")  # 建立 mytest2.R 的副本 mytest3.R
  ```

- **刪除檔案**：
  ```r
  file.remove("mytest2.R")  # 刪除 mytest2.R
  ```

---

### **4. 檔案與資料夾的路徑管理**
- **取得檔案的完整路徑**：
  ```r
  file.path("mytest3.R")  # 顯示 mytest3.R 的完整路徑
  ```

- **建立多層資料夾**：
  ```r
  dir.create(file.path("testdir2", "testdir3"), recursive = TRUE)
  ```
  - `recursive = TRUE`：確保可以一次性建立多層目錄。

---

### **5. 回復原本的工作環境**
- **切換回原本的工作目錄**：
  ```r
  setwd(old.dir)  # 回到原本的工作目錄
  ```

- **刪除剛剛建立的資料夾**：
  ```r
  unlink("testdir", recursive = TRUE)  # 刪除 testdir 及其內所有檔案
  ```

---

### **6. 課程重點**
✔ 使用 `getwd()` 和 `setwd()` 來管理工作目錄。  
✔ 使用 `dir.create()` 建立資料夾，並用 `file.create()` 來建立檔案。  
✔ 檢查檔案是否存在 (`file.exists()`)、檢視檔案資訊 (`file.info()`)。  
✔ 透過 `file.rename()` 和 `file.copy()` 來管理檔案名稱與備份。  
✔ `file.path()` 可用來建立與操作跨平台的路徑。  
✔ `unlink()` 可用來刪除資料夾及其內容。  
---


