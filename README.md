🌾 RiceSense AI Chatbot
Trợ lý AI nhận diện bệnh lá lúa – Công ty Nông Trí Việt

RiceSense là hệ thống chatbot thông minh hỗ trợ nông dân, hợp tác xã và nhà nghiên cứu trong việc nhận diện bệnh lá lúa, tư vấn xử lý và cung cấp kiến thức nông nghiệp.
Hệ thống sử dụng kết hợp:

RAG (Retrieval-Augmented Generation)

FAISS + SentenceTransformer để truy xuất tri thức bệnh lúa

GPT (gpt-4o-mini) để tạo câu trả lời tự nhiên, chính xác

Dataset bệnh lá lúa (8 lớp bệnh) do bạn cung cấp

Giao diện được xây dựng bằng Streamlit, backend bằng FastAPI.

📁 Cấu trúc dự án
├── RAG_chatbot.py            # API backend FastAPI – xử lý RAG & GPT
├── streamlit_chat.py         # Giao diện người dùng (Streamlit UI)
├── MC_chatbot.csv            # Bộ tri thức: Q&A về bệnh lúa / RiceSense
├── chat_history.csv          # Lịch sử hội thoại
├── feedback.csv              # Phản hồi đánh giá người dùng
├── requirements.txt          # Danh sách thư viện
├── .env                      # Biến môi trường (OPENAI_API_KEY, ADMIN_PASSWORD)
├── README.md                 # Tài liệu dự án (file này)

⚙️ Hướng dẫn cài đặt & chạy trên máy (Local)
1️⃣ Cài thư viện
python -m venv venv
# Windows:
venv\Scripts\activate

pip install -r requirements.txt

2️⃣ Thiết lập file .env

Tạo file .env trong thư mục dự án:

OPENAI_API_KEY=your_openai_key
ADMIN_PASSWORD=admin123
BACKEND_URL=http://localhost:8000


🔑 API key lấy tại: https://platform.openai.com

3️⃣ Chạy backend (FastAPI)
uvicorn RAG_chatbot:app --reload


Backend chạy tại:
👉 http://localhost:8000/chat
👉 Kiểm tra: http://localhost:8000/health

4️⃣ Chạy giao diện Streamlit
streamlit run streamlit_chat.py


Frontend tại:
👉 http://localhost:8501

🧠 Tính năng nổi bật
🌾 1. Trợ lý AI bệnh lá lúa

Trả lời câu hỏi về:

Nhận diện các bệnh: bạc lá, đạo ôn, đốm nâu, Leaf Scald, Rice Hispa, Narrow Brown Leaf Spot,…

Dấu hiệu bệnh, nguyên nhân, thời tiết / dinh dưỡng ảnh hưởng

Biện pháp phòng trừ đúng kỹ thuật

🔍 2. Truy xuất tri thức FAISS + SentenceTransformer

Sử dụng vector embedding để tìm câu trả lời phù hợp nhất trong MC_chatbot.csv

Trả lời nhanh – không gọi GPT nếu không cần

🤖 3. GPT hỗ trợ nâng cao

GPT chỉ được dùng khi tri thức không đủ chính xác

Ngôn ngữ trả lời theo người dùng (Việt/Anh)

💬 4. Lịch sử hội thoại & phản hồi người dùng

Tự động lưu vào CSV

Admin xem lại trong dashboard

📊 5. Dashboard quản trị

Xem lịch sử chat

Thống kê 10 câu hỏi phổ biến nhất

Xem feedback

🌐 6. Hỗ trợ song ngữ

Tự phát hiện tiếng Anh / Việt

Tự động dịch câu hỏi để RAG hoạt động chính xác

🚀 Deploy trên Streamlit Cloud (Frontend)

Backend FastAPI phải deploy riêng (Render/Railway/VPS)

Các bước:

Push code lên GitHub

Truy cập https://streamlit.io/cloud

Chọn file chạy: streamlit_chat.py

Thêm biến môi trường:

OPENAI_API_KEY

ADMIN_PASSWORD

BACKEND_URL (điểm đến FastAPI backend)

🆕 Tính năng nâng cấp 2025
Tính năng	Trạng thái
Chuyển từ TF-IDF → FAISS	✅
Bộ tri thức bệnh lúa (150 Q&A)	✅
Giao diện tối UI đẹp – hiện đại	✅
Bộ lọc ngôn ngữ thông minh	✅
Dashboard thống kê nâng cao	✅
Reload cơ sở tri thức không cần redeploy	✅
👨‍🌾 Đối tượng sử dụng

Nông dân trồng lúa

Hợp tác xã nông nghiệp

Cán bộ khuyến nông

Học sinh – sinh viên nghiên cứu STEM

Startup Nông nghiệp thông minh

👨‍💻 Tác giả & Đóng góp

Dự án được phát triển trong khuôn khổ RiceSense – Nông Trí Việt
Hướng đến ứng dụng AI phục vụ sản xuất nông nghiệp, giúp nông dân nhận diện bệnh sớm, giảm chi phí và tăng năng suất.

Mọi đóng góp xin gửi qua GitHub hoặc email liên hệ.