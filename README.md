# Dự án Machine Learning: Dự đoán Nhân viên Nghỉ việc bằng CatBoost

## 📌 Tổng quan dự án

Dự án này xây dựng một **mô hình Machine Learning sử dụng CatBoost** để dự đoán khả năng **nhân viên nghỉ việc (Employee Attrition)** trong doanh nghiệp.

Mục tiêu của dự án là:

* Phân tích các yếu tố ảnh hưởng đến việc nghỉ việc của nhân viên
* Xây dựng mô hình dự đoán có hiệu suất tốt
* Áp dụng **Cross Validation và Hyperparameter Tuning** để cải thiện mô hình

Dataset sử dụng trong dự án gồm:

* **1470 dòng dữ liệu**
* **35 cột đặc trưng**

---

# 🎯 Bài toán

Đây là bài toán **Binary Classification**:

| Giá trị | Ý nghĩa                     |
| ------- | --------------------------- |
| 0       | Nhân viên tiếp tục làm việc |
| 1       | Nhân viên nghỉ việc         |

Việc dự đoán trước khả năng nghỉ việc giúp doanh nghiệp:

* Giảm chi phí tuyển dụng
* Cải thiện chính sách giữ chân nhân viên
* Hiểu rõ các yếu tố ảnh hưởng đến sự gắn bó của nhân viên

---

# 🛠 Công nghệ sử dụng

* Python
* Pandas
* Scikit-learn
* CatBoost
* Matplotlib
* Jupyter Notebook

---

# ⚙️ Pipeline xây dựng mô hình

Quy trình xây dựng mô hình trong dự án gồm các bước sau:

### 1️⃣ Khám phá và tiền xử lý dữ liệu

* Đọc và kiểm tra dataset
* Xác định các **biến categorical**
* Chuẩn bị dữ liệu cho quá trình huấn luyện

### 2️⃣ Chia tập dữ liệu

Dataset được chia thành:

* **Train set**: dùng để huấn luyện mô hình
* **Test set**: dùng để đánh giá cuối cùng

---

### 3️⃣ Huấn luyện mô hình cơ bản (Baseline Model)

Huấn luyện một mô hình CatBoost với tham số cơ bản để làm **mốc so sánh ban đầu**.

---

### 4️⃣ Cross Validation

Áp dụng **Cross Validation** để:

* Đánh giá mô hình ổn định hơn
* Giảm nguy cơ overfitting
* Ước lượng hiệu suất mô hình tốt hơn trên dữ liệu chưa thấy

---

### 5️⃣ Hyperparameter Tuning

Tìm bộ tham số tối ưu cho mô hình.

Một số tham số được điều chỉnh:

* `depth`
* `learning_rate`
* `iterations`
* `l2_leaf_reg`

---

# 📈 Kết quả mô hình

| Mô hình             | ROC-AUC   |
| ------------------- | --------- |
| CatBoost Baseline   | ~0.78     |
| CatBoost sau tuning | **~0.82** |

Việc tuning tham số giúp **cải thiện hiệu suất mô hình** so với baseline.

---

# 🔎 Feature Importance

Các đặc trưng quan trọng nhất ảnh hưởng đến khả năng nghỉ việc:

| Feature              | Importance |
| -------------------- | ---------- |
| OverTime             | 16.46      |
| JobRole              | 11.31      |
| StockOptionLevel     | 9.49       |
| YearsWithCurrManager | 7.29       |
| Age                  | 7.15       |
| MonthlyIncome        | 5.63       |

Một số insight đáng chú ý:

* Nhân viên **làm thêm giờ nhiều** có xu hướng nghỉ việc cao hơn
* **Mức lương và vị trí công việc** ảnh hưởng đáng kể đến quyết định nghỉ việc
* **Thời gian làm việc với quản lý hiện tại** cũng là yếu tố quan trọng

---

# 📊 Ý nghĩa của dự án

Dự án giúp:

* Thực hành xây dựng pipeline **Machine Learning end-to-end**
* Áp dụng **CatBoost cho dữ liệu dạng bảng (tabular data)**
* Hiểu cách **tuning mô hình và đánh giá bằng ROC-AUC**

---

# ▶️ Hướng dẫn chạy dự án

### 1️⃣ Clone repository

```bash
git clone https://github.com/buitrongtrinh/Employee-attrition-prediction-catboost.git
```

---

### 2️⃣ Di chuyển vào thư mục dự án

```bash
cd catboost-employee-attrition
```

---

### 3️⃣ Cài đặt thư viện cần thiết

```bash
pip install pandas scikit-learn catboost matplotlib jupyter
```

---

### 4️⃣ Chạy Jupyter Notebook

```bash
jupyter notebook
```

Sau đó mở file notebook:

```
training_catboost.ipynb
```

và chạy các cell để thực hiện toàn bộ quá trình:

* tiền xử lý dữ liệu
* huấn luyện mô hình
* tuning tham số
* đánh giá kết quả

---

# 🚀 Hướng phát triển thêm

Một số cải tiến có thể thực hiện trong tương lai:

* Sử dụng **Optuna hoặc Bayesian Optimization** để tối ưu tham số
* Áp dụng **SMOTE** để xử lý dữ liệu mất cân bằng
* Phân tích **SHAP values** để giải thích mô hình
* Triển khai mô hình thành **API bằng FastAPI**

---

# 👨‍💻 Tác giả

**Trịnh Bùi Trọng**

Dự án được thực hiện nhằm mục đích học tập và thực hành Machine Learning với dữ liệu thực tế.
