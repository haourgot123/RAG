# Synthetic data

- Dữ liệu là nguyên liệu thô cho AI
- Dữ liệu càng nhiều AI càng thông mình
- Dữ liệu giúp các mô hình AI cải thiện theo thời gian.

# Quy trình chuẩn bị dữ liệu
- Thu thập dữ liệu: Dữ liệu được thu thập từ nhiều nguồn khác nhau như: web, mạng xã hội, thiết bị IoT, ....
- Xử lí dữ liệu: Dữ liệu được làm sạch, tổ chức và chuẩn bị cho việc huấn luyện mô hình.
- Huấn luyện mô hình: Mô hình AI được huấn luyện dựa trên dữ liệu đã được xử lí.
- Triển khai mô hình: Mô hình được triển khai cho mục đích sử dụng thực tế.
- Thu thập dữ liệu mới: Dữ liệu mới được thu thập để cải thiện LLM theo thời gian.

# Synthetic Data là gì?
- Việc phụ thuộc vào con người khiến cho nguồn cung cấp dữ liệu bị khan hiếm
- Các mô hình GenAI hay Stable Diffsion đã có thể tạo ra văn bản, hình ảnh có chất lượng ngang con người. Vậy dữ liệu 'ảo' chính là xu hướng của thế giới.
- Synthetic data bao gồm việc sử dụng AI để tạo ra dữ liệu huấn luyện AI.

# Vì sao nên sử dụng Synthetic Data
1. Hiệu quả:
    - Có thể được tạo ra nhanh chóng hơn so với human data.
    - Có thể tạo ra với chi phí thấp hơn so với human data.
    - Có thể tạo ra với chất lượng và độ chính xác cao.
2. Tính bảo mật:
    - Không chứa thông tin cá nhân.
    - Có thể sử dụng để mô phỏng các TH nhạy cảm mà k cần thu thập dữ liệu thực tế.

# Mục đích của Synthetic data
- Hiện tại Synthetic data được chia thành 2 mục đích:
    - Tạo dữ liệu để pretraining (ít, chỉ bigtech làm).
    - Tạo dữ liệu để finetune cho task cụ thể.
# Sử dụng Synthetic data trong finetuning
- Việc finetuning mô hình theo hướng hỏi đáp cần nhiều cặp Question/Answer
    - Trước đây cần người trong việc này dẫn đến tăng chi phí và thời gian.
- Kết hợp RAG, Synthetic Data có thể được tạo ra dễ dàng với từng usecase cụ thể.
- Tuỳ vào độ dài của vănn bản nội bộ mô hình thường chỉ cần 100 - 1000 câu hỏi để hiểu hơn về bài toán hiện tại.

# Model Merging
- Cho phép các model có thể kết hợp với nhau để trở thành mô hình mạnh hơn.

