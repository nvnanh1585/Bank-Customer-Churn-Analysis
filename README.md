# Dự án: Dự báo Khách hàng Rời bỏ (Customer Churn Prediction)

## Tổng quan

Dự án này phân tích hành vi khách hàng trong lĩnh vực **ngân hàng** và xây dựng mô hình học máy để **dự báo khả năng khách hàng rời bỏ dịch vụ (customer churn)**.

Mục tiêu của dự án là xác định các yếu tố liên quan đến hành vi rời bỏ và xây dựng mô hình dự đoán xác suất churn, từ đó giúp ngân hàng có thể triển khai **các chiến lược giữ chân khách hàng hiệu quả hơn**.

Quy trình thực hiện bao gồm:

* Tiền xử lý dữ liệu
* Phân tích khám phá dữ liệu (EDA)
* Feature engineering
* Lựa chọn biến
* Xây dựng và đánh giá mô hình

---

# Bài toán kinh doanh

Trong ngành ngân hàng, việc mất khách hàng có thể gây tổn thất lớn vì **chi phí thu hút khách hàng mới thường cao hơn nhiều so với chi phí giữ khách hàng hiện tại**.

Dự án này nhằm:

* Phân tích đặc điểm của nhóm khách hàng rời bỏ
* Xác định các yếu tố ảnh hưởng đến hành vi churn
* Xây dựng mô hình dự đoán xác suất khách hàng rời bỏ

Kết quả của mô hình có thể hỗ trợ ngân hàng trong việc:

* Xác định nhóm khách hàng có nguy cơ rời bỏ cao
* Triển khai các chương trình giữ chân khách hàng phù hợp

---

# Dữ liệu

Bộ dữ liệu gồm khoảng **80.000 quan sát khách hàng**, bao gồm các thông tin về nhân khẩu học, tài chính và hành vi sử dụng dịch vụ ngân hàng.

Các nhóm biến chính gồm:

### Thông tin nhân khẩu học

* Tuổi
* Giới tính

### Chỉ số tài chính

* Số dư tài khoản (Balance)
* Thu nhập ước tính (Estimated Salary)

### Hành vi sử dụng dịch vụ

* Số lượng sản phẩm ngân hàng
* Sở hữu thẻ tín dụng
* Trạng thái khách hàng hoạt động

### Biến mục tiêu

* **Exited**

  * 1: Khách hàng rời bỏ
  * 0: Khách hàng tiếp tục sử dụng dịch vụ

---

# Phương pháp thực hiện

Dự án được triển khai theo quy trình phân tích dữ liệu tiêu chuẩn:

1. Tiền xử lý dữ liệu
2. Phân tích khám phá dữ liệu (EDA)
3. Feature engineering
4. Feature selection
5. Xây dựng mô hình
6. Đánh giá mô hình

---

# Tiền xử lý dữ liệu

Các bước tiền xử lý bao gồm:

* Xử lý dữ liệu thiếu
* Mã hóa biến phân loại bằng **One-Hot Encoding**
* Chuẩn hóa các biến số
* Chia dữ liệu thành **training set** và **test set**

Các bước này giúp dữ liệu phù hợp để sử dụng trong mô hình học máy.

---

# Phân tích khám phá dữ liệu (EDA)

EDA được thực hiện để hiểu rõ hơn về đặc điểm của khách hàng và các yếu tố liên quan đến churn.

Các phân tích chính bao gồm:

* Phân bố độ tuổi và đặc điểm khách hàng
* Tỷ lệ churn theo từng nhóm tuổi
* Mối quan hệ giữa số dư tài khoản, thu nhập và churn
* Phân tích tương quan giữa các biến

Các biểu đồ trực quan như **distribution plots, biểu đồ so sánh churn và heatmap tương quan** được sử dụng để hỗ trợ phân tích.

---

# Feature Engineering

Một số biến mới được tạo ra để phản ánh hành vi tài chính của khách hàng:

* **Income_Balance_Ratio**
* **Balance_per_Service**
* **Card_Service_Ratio**

Các biến này giúp mô hình nắm bắt tốt hơn mối quan hệ giữa **khả năng tài chính và mức độ sử dụng dịch vụ ngân hàng**.

---

# Lựa chọn biến (Feature Selection)

Phương pháp **L1 regularization (Lasso)** được sử dụng để lựa chọn các biến quan trọng nhất cho mô hình.

Việc này giúp:

* Giảm độ phức tạp của mô hình
* Hạn chế overfitting
* Tăng khả năng diễn giải của mô hình

---

# Mô hình

Mô hình chính được sử dụng trong dự án là **Logistic Regression**, một phương pháp phổ biến cho bài toán phân loại nhị phân như dự đoán churn.

Hiệu suất mô hình được đánh giá thông qua các chỉ số:

* ROC-AUC
* Precision
* Recall
* Cross-validation

---

# Kết quả

Mô hình Logistic Regression đạt được các kết quả sau trên tập test:

* **ROC-AUC:** ~0.82
* **Precision:** ~93%
* **Recall:** ~77%

Kết quả cho thấy mô hình có khả năng khá tốt trong việc xác định những khách hàng có nguy cơ rời bỏ.
