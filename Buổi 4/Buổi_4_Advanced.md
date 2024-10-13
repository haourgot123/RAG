# Buổi 4 Các kĩ thuật nâng cao LLM

# Vì sao cần tinh chỉnh các tham số LLM
- Việc điều chỉnh tham số rất quan trọng để tối ưu hoá hiệu suât và chất lượng đầu ra của mô hình ngôn ngữ lớn (LLM) trong môi trường production.
- Các siêu tham số như Temperature, Top-k, Top-p, Repetition Penalty và Maximum length cho phép kiểm soát sự đa dạng, tính tập trung và độ dài văn bản được tạo ra.

# Tham số : Model Size

- Tên của các mô hình ngôn ngữ (Open-source) thường đi kèm với các tag là 7B, 13B, 33B,.. - đây chính là size của mô hình.
- Mô hình càng lớn, khả năng lưu trữ càng lớn, khả năng xử lí task tốt hơn.
- Điểm yếu của mô hình ngôn ngữ lớn là triển khai đắt vì đòi hỏi phần cứng cao và xử lí chậm.
- 2 size phổ biến là 7B và 13B

# Tham số: Temperature
- Temperature là một siêu tham số quan trọng kiểm soát tính ngẫu nhiên và đa dạng của văn bản được tạo ra bởi LLM.
- Giá trị temperature giao động từ  0 - 1
- Việc điều chỉnh Temperature cho phép kiểm soát sự sáng tạo và đa
dạng của văn bản sinh ra, tùy thuộc vào mục đích sử dụng cụ thể.

# Tham số: Top - p và Top - k

- Top-p và Top-k là hai phương pháp sampling được sử dụng để lựa chọn token tiếp theo trong quá trình sinh văn bản của LLM.
- Top-k Sampling: Chỉ xem xét top k token có xác suất cao nhất để lựa chọn làm token tiếp theo.
- Top-p Sampling: Lựa chọn tập hợp token nhỏ nhất sao cho tổng xác suất vượt ngưỡng p (thường p = 0.9)

# Tham số: Frequency Penalty
- Điều chỉnh xác suất sinh ra các token xuất hiện thường xuyên trong dữ liệu huấn luyện.
- Giá trị dương làm giảm xác suất sinh ra các token phổ biến, khuyến khích sử dụng từ hiếm hoặc cụ thể hơn.

Ví dụ: "Hôm nay trời nắng đẹp, thích hợp để [đi chơi ngoài trời /
dạo bộ trong công viên]."

Với Frequency Penalty cao,"dạo bộ trong công viên" có thể được
ưu tiên hơn "đi chơi ngoài trời".

# Tham số: Presence Penalty
- Điều chỉnh xác suất sinh ra các token chưa xuất hiện trong câu đầu vào.
- Giá trị dương làm giảm xác suất sinh ra các token không liên quan trực tiếp đến ngữ cảnh.

Ví dụ: "Tôi thích chơi bóng đá và [bơi lội / xem phim]."

Với Presence Penalty cao, "bơi lội" có thể được ưu tiên hơn "xem
phim" vì liên quan đến chủ đề thể thao.

# Tham số: Sequence Length / Max Tokens
- Kiểm soát độ dài tối đa của văn bản được sinh ra.
- Lưu ý khi chọn giá trị Max Tokens:

    Cần cân nhắc yêu cầu về độ dài và mức độ chi tiết của văn bản
    đầu ra.
    Giá trị quá lớn có thể dẫn đến văn bản dài dòng, lan man và tốn
    nhiều tài nguyên tính toán.
    Giá trị quá nhỏ có thể khiến văn bản đầu ra không đầy đủ thông
    tin hoặc bị cắt ngắt đột ngột.
- Một số context length phổ biến: 2048, 4096 và 8192

# Function Calling

- Là một tính năng nâng cao của LLM, cho phép người dùng thực hiện một số hoạt động:
    
    - Nhận các hàm do người dùng định nghĩa làm đầu vào.
    - Tạo ra dữ liệu JSON có cầu trúc thông qua các hàm tuỳ chỉnh 
    - Giải quyết vấn đề kết quả văn bản không nhất quán và khó đoán.
    - Truy cập API web bên ngoài, thực thi quyền truy vấn SQL tuỳ chỉnh.
    - Trích xuất thông tin liên quan từ văn bản
    - Cung cấp phản hồi nhất quán cho các lệnh SQL và API

# Vì sao cần đến Function Calling
- Vì ChatGPT là 1 mô hình chat được làm định hướng theo con người:
    
    - Giảm độ chính xác, ổn định trong các ứng dụng cần ChatGPT để tự động hoá.
    - Các nhà phát triển quen làm việc với các dữ liệu có cấu trúc.
    - Cần sử dụng RegEX hoặc prompt engineering để trích xuất thông tin từ chuỗi văn bản, tốn thời gian và công sức.


# Assistant API

- API Assistants cho phép bạn xây dựng các trợ lý AI trong
ứng dụng của riêng mình.
- Một Assistant có các hướng dẫn và có thể tận dụng các
mô hình, công cụ và kiến thức để trả lời các truy vấn của
người dùng.
- API Assistants hiện hỗ trợ ba loại công cụ: Code
Interpreter , Retrieval và Function calling.
- Assistant có thể tạo dễ dàng với các công cụ có sẵn:

    - Code Intepreter: Cho phép GPT chạy code để đưa ra đáp án thay vì sử dụng câu trả lời đơn thuần
    - Retrieval: Cho phép upload các file PDF, Docx để làm RAG
    - Functions: Tự thêm tool của chính mình
