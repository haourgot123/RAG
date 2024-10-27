# Open Source LLM

# Một số Open Source nổi tiếng 

- Llama: được phát triển bởi MetaAI
- Mistral: Open Source nổi tiếng nhất hiện tại
- Qwen : Được phát hành bởi Alibaba, một LLM đa ngôn ngữ tốt nhất 
- BLOOM: LLM đa ngôn ngữ đầu tiên trên thế giới

# Các Open Source nổi tiếng Tiếng Việt
- Vietcuna: Được xây dựng từ mô hình BLOOM
- VinaLlama & VBD-Llama2: Được xây dựng từ Llama2
- Vistral: Dựa trên mô hình Mistral

# HuggingFace
- Nền tảng nguồn mở cho AI
- Cung cấp thư viẹn và công cụ để huấn luyện, chia sẻ và triển khai các mô hình AI.
- Tập trung vào xử lí ngôn ngữ tự nhiên và thị giác máy tính
- Một số thư viện con của HuggingFace:
    - Transformers: Thư viện dành cho các kiến trúc transformers SOTA
    - Datasets: Kho lưu trữ tập dữ liệu có sẵn để huấn luyện mô hình.
    - Tokenizers: Thư viện dùng để tiền xử lí văn bản với hiệu suất cao.
    - Accelerate: Tối ưu hoá việc huấn luyện trên nhiều GPU/TPU

# Transformer
- Thư viện Python cho các mô hình Transformers SOTA
- Hỗ trợ nhiều kiến trúc: BERT, GPT, Llama, Qwen, Mistral/Mixtral
- Dễ dàng tải và huấn luyện
- Tiền xư lí dữ liệu và tinh chỉnh đơn giản

# Datasets
- Kho lưu trữ dữ liệu cho NLP, CV, Audio, ..
- Giao diện thống nhất để tải, lưu trữ và truy vấn
- Hỗ trợ định dạng: CSV, JSON, Parquet,...
- Tích hợp với Transformers để xử lí dữ liệu

# Accelerate
- Đơn giản hoá việc huấn luyện mô hình trên nhiều GPU/TPU
- Tự động chia tải batch và đồng bộ hoá gradient
- Hỗ trợ kiểm tra (checkpoint) và phục hồi huấn luyện.
- Tích hợp transformer và pytorch

# Training và Finetuning

##  Vì sao cần Finetune LLM?
- Cải thiện hiệu suất cho các tác vụ cụ thể.
- Tạo ra các mô hình chuyên biệt.
- Tiết kiệm thời gian và chi phí.

## Các loại training 
- Pretrain(Tiền huấn luyện)
- Finetuning (Tinh chỉnh)
- Human Aligment: Sử dụng RL với phản hồi của con người để điều chỉnh hành vi của LLM

# Dữ liệu khi FineTune
- Dữ liệu khi FineTune thường nằm ở dạng Question/Answer
- Có 2 tiêu chuẩn để setup dữ liệu là `Alpaca`  và `ShareGPT`
# Thư viện khi FineTune
- 2 thư viện phổ biến nhất dùng để FineTune :`Axolotl` và `Llama-Factory`.
- Hỗ trợ các thuật toán tối ưu như: Flash Attention và DeepSpeed

# Efficient FineTuning
- Sử dụng kĩ thuật `LoRA` hay `QLoRA` để giải quyết vấn đề này.

# LoRA và QLoRA

## LoRA (Low-Rank Adaptation)
- Thêm ma trận `adapter` nhỏ, có thể huấn luyện được vào các lớp LLM hiện có.
- Thay đổi hành vi mô hình mà không làm thay đổi số lượng lớn các tham số ban đàu
- Hiệu quả và ít khả năng overfiting hơn.

# QLoRA (Quantized LoRA)
- Kết hợp LoRA với lượng tử hoá.
- Kích thước mô hình nhỏ hơn để triển khai trên các thiết bị yếu.
- Duy trì độ chính xác so với các phương pháp FineTune đầy đủ.

# Một số tham số lưu ý khi làm FineTune
- Learning Rate: 1e-3 ~ 1e-6
- Context Length: 1024, 2048, 4096, 8192
- Optimizer: thường tiết kiện chọn `adamw_bnb_8bit`
