# Buổi 5: Giới thiệu về Agents và tự động hoá



# Chain of Thought
- Là 1 kĩ thuật để cải thiện hiệu suất của LLM trong các tác vụ lập luận phức tạp
- Nó liên quan đến việc cung cấp các bước lập luận trung gian như một phần của đầu vào để hướng dẫn LLM tạo ra kết quả mong muốn.


# Lợi ích của CoT
- Cải thiện hiệu suất trong các tác vụ lập luận nhiều bước.
- Tăng cường khả năng giải thích đầu ra của LLM
- Khả năng xử lí các câu hỏi phức tạp và tinh tế hơn.

# Ứng dụng của CoT
- Trả lời câu hỏi
- Giải quyết vấn đề
- Ra quyết định

# Agents
- Agents là các thực thể tự trị có khả năng nhận thức lập luận và hành động trong một môi trường nhất định.
- Mục tiệu của Agents là hoàn thành các nhiệm vụ hoặc mục tiêu thông qua tương tác với môi trường.

# Các đặc tính của Agents
- Tự trị (Autonomy): Không cần sự can thiệp của con người, và hành động theo nhận thức của chúng về môi trường.
- Tương tác (Interactivity): Liên tục tương tác với môi trường để thu thập thông tin và các tác động lên nó.
- Thích nghi (Adaptability): Thích nghi với sự thay đổi của môi trường và tự điều chỉnh hành vi của mình dựa trên phản hồi hoặc kinh nghiệm thu được từ các tương tác trước đó.
- Mục tiêu và định hướng (Goal-orented): Agents hoạt động với mục đích đạt được các mục tiêu cụ thể. Chúng lập luận để đưa ra hành động tốt nhất để đạt được mục tiêu.

# Các thành phần của Agents
- Nhận thức: Agents thu thập thông tin và biểu diễn thành các biểu diễn nội bộ mà agents có thể hiểu được
- Lập luận và đưa ra quyết đinh: Agents sẽ dựa vào môi trường để đưa ra quyết định tốt nhất.
- Hành động: Agents sẽ thực hiện các hành động đã chọn trong môi trường.
- Học tập: Agents có thể cải thiện hiệu suất của mình theo thời gian thông qua việc học tập.

# ReAct
- Là 1 framework để xây dựng các LLM agents có khả năng lập luận và hành động.
- ReAct kết hợp khả năng suy luận của LLM và khả năng tương tác với môi trường bên ngoài.
- Mục tiêu của ReAct là tạo ra các agents có thể hoàn thành các nhiệm vụ phức tạp thông qua 1 chuỗi các hành động và lập luận.
- ReAct tạo ra 1 vòng lặp Nhận thức và Hành động để Agents có thể liện tục cập nhật kiến thức.

# Các thành phần chính của ReAct
## Lập luận
- LLMs sử dụng các embedding môi trường và kiến thức nền tảng để lập luận về trạng thái hiện tại và đưa ra lập luận và hành động tiếp theo.
- Quá trình lập luận có thể bao gồm nhiều bước, sử dụng các kĩ thuật như CoT để tạo ra các bươc lập luận chi tiết.
- Kết quả của quá trình lập luận là 1 kế hoạch hành động hoặc 1 tập hợp các hành động tiềm năng.

## Hành động
- Dựa trên kết quả lập luận, agents chọn 1 hành động để thực thi trong môi trường.
- Hành động có thể là lệnh văn bản, lệnh gọi API, ...
- Sau khi hành động thì agents sẽ nhận phản hồi từ môi trường và quá trình nhận thức - lập luận - hành động sẽ lặp lại.

## Thought
- LLM suy nghĩ để lựa chọn hành động tiếp theo.
## Action 
- LLM chọn một hành động/công cụ đã được cho để thực hiện hành động.
## Action Input
- LLM sẽ tạo ra input cho công cụ được cho.
## Observation
- Output từ công cụ được sử dụng

# RAISE
- RAISE là một cải tiến của mô hình ReAct
- RAISE bổ sung thêm 2 thành phần bộ nhớ, tương tự như bộ nhớ ngắn hạn và dài hạn của con người:
    - Scrathpad: Lưu trữ thông tin và kết luận quan trọng từ các tương tác gần đây
    - Retrieval module: Truy xuất các ví dụ liên quan đến ngữ cảnh hiện tại.
- RAISE được thiết kế để kiểm soát và thích nghi với các đoạn hội thoại phức tạp.
# Quy trình xây dựng RAISE
- RAISE được xây dụng bao gồm các pha:
    - Chọn lọc hội thoại
    - Trích xuất hoàn cảnh
    - Hoàn thiện chuỗi suy nghĩ  - CoT
    - Mở rộng cảnh
    - Huấn luyện LLM
- Cách tiếp cận có cấu trúc này giúp phát triển tốt hơn về khả năng xử lí ngôn ngữ, nhận thức ngữ cảnh và thích nghi với các tình huống hội thoại đa dạng.
