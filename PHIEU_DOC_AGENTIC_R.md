# Phiếu đọc bài số 6 — Agentic-R

Bài: Agentic-R: Learning to Retrieve for Agentic Search, Liu và cộng sự, Findings of ACL 2026.

Nguồn: https://aclanthology.org/2026.findings-acl.785.pdf

Đây là phiếu để tự điền bằng lời mình, chưa phải báo cáo hoàn chỉnh.

## 0. Tóm tắt sau khi đóng PDF

- **Bài giải quyết vấn đề gì?** Huấn luyện bộ truy xuất (retriever) để lấy được đoạn văn giúp agent trả lời đúng câu hỏi qua nhiều lượt tìm kiếm. (Abstract, §1, PDF tr. 1–2)
- **Vì sao cách trước còn hạn chế?** Một đoạn có thể đúng chủ đề mà vẫn thiếu dữ kiện agent cần. Ví dụ, khi truy vấn tìm năm sinh, đoạn kể về sự nghiệp có thể nhắc đúng người nhưng chỉ hữu ích nếu cung cấp năm sinh hoặc đầu mối để tìm tiếp. (Abstract, §1, PDF tr. 1–2; ví dụ năm sinh là minh họa)
- **Ý tưởng mới là gì?** Dùng hai tín hiệu để chọn đoạn văn huấn luyện retriever: mức liên quan với truy vấn ở lượt hiện tại (local relevance) và độ đúng của câu trả lời cuối khi agent đi tiếp từ đoạn đó (global answer correctness). Bài còn huấn luyện luân phiên agent và retriever. Cần tự kể lại thứ tự cập nhật ở Lượt 2. (Abstract, §4, PDF tr. 1, 3–6)
- Bằng chứng quan trọng nhất là gì?
- Điều gì bài chưa chứng minh được?

## 1. Bài toán nghiên cứu

- **Vấn đề cụ thể:** Chọn thông tin hữu ích cho câu trả lời cuối khi agent tự sinh truy vấn trong quá trình suy luận nhiều lượt.
- **Nhánh nghiên cứu trong Agentic Retrieval:** Học bộ truy xuất phục vụ tìm kiếm nhiều lượt, kết hợp tối ưu luân phiên với search agent.
- **Input/output của nhiệm vụ:** Hệ thống nhận câu hỏi gốc `Q` và sinh đáp án cuối `A`. Ở mỗi lần tìm kiếm, agent sinh truy vấn `q_i`, retriever lấy tập đoạn văn `D_i` từ kho tài liệu và hệ thống đưa tập này vào ngữ cảnh để agent đọc tiếp. Agent quyết định dừng tìm khi đánh giá đã đủ dữ kiện. Kho tài liệu dùng trong thực nghiệm của bài là Wikipedia.
- **Hạn chế trước:** Độ tương đồng ngữ nghĩa cho biết đoạn văn gần với truy vấn về mặt nội dung. Để giúp agent, đoạn văn còn cần cung cấp dữ kiện hoặc đầu mối giúp giải câu hỏi gốc.
- **Ví dụ từ Hình 1:** Agent tìm được ngày sinh của John William Henry II ở lượt đầu. Sau đó nó đặt truy vấn `Jed Hoyer birth year` để tìm dữ kiện còn thiếu, rồi dùng thông tin tích lũy để trả lời ai lớn tuổi hơn.
- **Nguồn trang/mục:** Abstract, §1 và Hình 1 (PDF tr. 1–2), §3 (tr. 3), §4 (tr. 3–6), §5.1 về kho tài liệu (tr. 6).

## 2. Phương pháp

- Các thành phần:
- Sơ đồ sử dụng khi trả lời một câu hỏi:
- Sơ đồ tạo dữ liệu và huấn luyện:
- Vai trò local relevance:
- Vai trò global answer correctness:
- Thứ tự chọn positive/negative:
- Input retriever:
- Agent tự quyết định gì?
- Quy tắc con người đặt trước:
- Khi nào retrieve, query sinh thế nào, điều kiện dừng:
- Cải tiến chính:
- Nguồn trang/mục/hình:

## 3. Huấn luyện

| Thành phần | Dữ liệu/input | Cách học | Loss/reward | Phần giữ cố định | Nguồn |
|---|---|---|---|---|---|
| Retriever | | | | | |
| Search agent | | | | | |

- Kể lại một vòng tối ưu:
- Gold answer dùng ở đâu?
- Hai kiểu vòng lặp khác nhau thế nào?
- Ký hiệu/công thức còn chưa hiểu:

## 4. Thực nghiệm

- Dataset train:
- Dataset đánh giá và quy mô (ghi nguồn, không đoán):
- Metric và cách tính:
- Baseline và vì sao chọn:
- LLM/retriever/kho tài liệu:
- Ngân sách search, số passages, số vòng train:
- Những điều chưa tìm thấy trong bài:

| Agent / thiết lập | Dataset / nhóm dataset | Baseline | EM baseline | EM Agentic-R | Chênh lệch (điểm) | Bảng, dòng/cột |
|---|---|---|---:|---:|---:|---|
| | | | | | | |
| | | | | | | |

| Thành phần bị bỏ/thay | Cấu hình gốc để so | Metric trước → sau | Điều được hỗ trợ | Điều chưa đủ để kết luận | Nguồn |
|---|---|---|---|---|---|
| | | | | | |

- Hai hoặc ba kết quả nổi bật:
- Một ngoại lệ/trường hợp không tốt nhất:
- Search turns có chứng minh latency không? Vì sao?

## 5. Đánh giá

| Nhận xét | Căn cứ cụ thể | Phạm vi/giới hạn | Tác giả nêu hay mình suy luận? |
|---|---|---|---|
| Điểm mạnh | | | |
| Hạn chế | | | |
| Đánh đổi chi phí | | | |

- Trường hợp có thể phù hợp:
- Trường hợp cần kiểm chứng thêm:

## 6. Liên kết các bài khác

- So với Search-R1: giống/khác ở mục tiêu, thành phần được tối ưu và tín hiệu học:
- Quan hệ với ReAct/IRCoT/FLARE trong vòng agent–retrieval:
- Survey dữ liệu giúp hiểu hoặc đánh giá bài này thế nào?
- Khả năng bổ trợ và điều chưa được thực nghiệm:
- Nguồn và thông tin cần xác nhận với bạn cùng nhóm:

## 7. Nhật ký bằng chứng và câu hỏi

| Ý mình hiểu | Trang/mục/bảng | Câu hỏi/điểm chưa chắc |
|---|---|---|
| | | |

## 8. Kiểm tra trước khi gửi nhóm

- [ ] Điền đủ sáu mục hoặc ghi rõ thông tin chưa tìm thấy.
- [ ] Tự giải thích được hai sơ đồ.
- [ ] Phân biệt contrastive training của retriever và RL của agent.
- [ ] Không nhầm training với inference; không nhầm search turns với training iterations.
- [ ] Mỗi số liệu có đúng agent/dataset/bảng nguồn.
- [ ] Chênh lệch điểm phần trăm không bị gọi nhầm là phần trăm tương đối.
- [ ] Mỗi ablation so với đúng cấu hình gốc.
- [ ] Phân biệt tác giả báo cáo, nhóm tự chạy và mình suy luận.
- [ ] Có mối liên hệ với paper khác và ít nhất một nhận xét có giới hạn.
- [ ] Tập nói không nhìn tài liệu và đánh dấu câu chưa trả lời được.
