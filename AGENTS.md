# Agentic-R — hướng dẫn cho agent tiếp nhận

## Đọc trước khi làm

Đọc [HANDOFF.md](HANDOFF.md), sau đó [SOURCES.md](SOURCES.md). Đây là bộ tài liệu local để tiếp tục công việc mà không cần lịch sử chat. Trạng thái đang làm được duy trì ở HANDOFF; không nhân bản tiến độ vào nhiều file.

## Phạm vi đã được người dùng chốt

- Môn Khai phá dữ liệu; **nhóm 5**, chủ đề **Agentic RAG / Agentic Search**.
- Người dùng phụ trách **paper 6 theo sheet của cô**: **Agentic-R: Learning to Retrieve for Agentic Search**, Liu và cộng sự, Findings of ACL 2026.
- Ô phân công tương ứng: tab `Final`, ô **K7**. Survey Data-Centric ở F7 là paper 1 trong sheet; thứ tự của template nội bộ khác sheet. Người dùng đã sửa nhầm lẫn này hai lần; không nhận survey làm bài chính.
- Người dùng mới đọc paper lần đầu. Mục tiêu: hiểu, giải thích và viết báo cáo theo template, liên hệ với các bài nhóm đọc.
- Mốc làm việc hiện dùng: **12h thứ Bảy 21/11/2026**. Ảnh cũ ghi 27/11; không tự đổi lịch. Chưa xác nhận ngày thuyết trình riêng của nhóm.

## Nguồn và cách viết

- Dùng PDF chính thức [Paper_06_Agentic_R_ACL2026.pdf](Paper_06_Agentic_R_ACL2026.pdf) để kiểm chứng nội dung kỹ thuật. File text trích xuất chỉ hỗ trợ tìm kiếm; nhìn lại PDF khi đọc công thức, bảng và hình.
- Dùng yêu cầu cô và template trong `nguon_tham_khao/` theo chỉ dẫn SOURCES. Đề cương nhóm là kế hoạch, không phải bằng chứng các việc đã được thực hiện.
- Yêu cầu của cô: phân tích cơ chế và liên hệ giữa các nghiên cứu; viết tiếng Việt chính xác, trích dẫn thật, giải thích được khi hỏi đáp. Code chạy lại là điểm cộng, không bắt buộc. Báo cáo chung tối thiểu 30 trang; không áp 30 trang cho phần cá nhân.
- Tách số liệu tác giả, kết quả nhóm tự chạy và nhận xét suy luận. Mỗi số liệu ghi trang/mục/bảng, agent, dataset, baseline và thiết lập.
- Trọng tâm Agentic-R là học retriever; framework cũng tối ưu agent bằng RL theo các giai đoạn luân phiên. Không viết “chỉ train retriever”, không gán PPO làm loss của retriever.
- Phân biệt training/inference, search turns/training iterations, relevance/utility, điểm phần trăm/phần trăm tương đối. Đọc ablation theo đúng cấu hình đối chiếu.

## Làm việc và bàn giao

- Tiếp tục hướng dẫn hoặc viết phần được người dùng yêu cầu; không coi phiếu trống là bài hoàn thành. Không tự đổi paper hay nhận trách nhiệm thay cả nhóm.
- Giữ nguyên bản nguồn và ghi chú người dùng; dùng file mới cho báo cáo/slide khi được yêu cầu. Các bản tháng 10 trong `nguon_tham_khao/lich_su/` chỉ để tra bối cảnh.
- Dùng đường dẫn tương đối trong tài liệu để có thể sao chép cả thư mục sang agent hoặc máy khác. Không phụ thuộc đường dẫn Temp, session ID hay bộ nhớ riêng của agent.
- Nếu nhiều agent cùng làm: xác định file mỗi người sửa; trao đổi kết quả có nguồn; tích hợp vào HANDOFF sau khi kiểm tra. Không ghi đè thay đổi mới của agent khác.
- Khi kết thúc lượt có thay đổi: cập nhật ngày, việc đã làm, file thay đổi, kiểm chứng, việc còn lại và bước tiếp theo trong HANDOFF. Đánh dấu rõ điểm chưa chắc.
- Gói ZIP trong `handoff/` là snapshot ngày tạo; file đang làm bên ngoài ZIP mới là trạng thái hiện hành. Đóng gói lại nếu cần gửi phiên bản mới.
- Agent không tự đọc `AGENTS.md` cần được yêu cầu mở file này bằng prompt. Không hứa mọi công cụ đều tự nạp cùng một tên file.
