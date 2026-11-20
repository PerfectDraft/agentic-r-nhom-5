# Kế hoạch đọc Agentic-R cho người mới

## 1. Chốt đúng bài và mục tiêu

- Nhóm 5: Agentic RAG / Agentic Search.
- Bài số 6 theo sheet của cô: **Agentic-R: Learning to Retrieve for Agentic Search**, Wenhan Liu và cộng sự, Findings of ACL 2026.
- Trang chính thức: https://aclanthology.org/2026.findings-acl.785/
- PDF: https://aclanthology.org/2026.findings-acl.785.pdf
- Code tác giả: https://github.com/8421BCD/Agentic-R
- Sheet chia bài của cô: [Mở danh sách bài báo](https://docs.google.com/spreadsheets/d/196oE76vS1VhdpKABedS18KKUXDg2vZH_/edit?gid=1132376818#gid=1132376818) — tab `Final`, nhóm 5 ở hàng 7; bài số 6 **Agentic-R** tại ô **K7**.
- Template đọc của nhóm: https://docs.google.com/document/d/1G3k18IhIkDxbX8GoLGKHCK80EJ1LCVAj6o3uyw1_PQ0/edit
- Yêu cầu cô: https://docs.google.com/document/d/1uIi71u2jV41U7B3B03N7B4BDJ5U89-cvbUdlaacbGYo/edit

Lưu ý thứ tự: trong template nội bộ, Agentic-R đứng trước Data-Centric; trong sheet của cô, Data-Centric ở cột survey, Agentic-R ở cột số 6. Dùng thứ tự trên sheet cho nhiệm vụ này.

- **Mục tiêu hoàn thành cá nhân:** xong trọn gói việc đọc hiểu và điền đủ 6 mục trong [PHIEU_DOC_AGENTIC_R.md](PHIEU_DOC_AGENTIC_R.md) ngay **tối Thứ Năm 19/11/2026** (gói gọn trong **2 ngày 18–19/11**, để Thứ Sáu 20/11 hoàn toàn trống lịch).
- **Mốc báo lại với nhóm:** trước **12h Thứ Bảy 21/11/2026** theo nội dung template hiện hành và lời bạn nói (ảnh thông báo cũ ghi 27/11; giữ mốc sớm 21/11 để dự phòng và đối chiếu nhanh với bạn đọc Search-R1). Tài liệu cô quy định trình bày giữa kỳ ở tuần 13–15; chưa xác nhận ngày riêng của nhóm.

Mục tiêu cuối ngày 19/11: tự nói được vấn đề, giải thích Figure 2, tách được huấn luyện agent/retriever, đọc được Tables 1–2, đưa ra nhận xét có nguồn, viết sẵn khung liên hệ với bài Search-R1 và hoàn thiện phiếu đọc 6 mục. Không cần thuộc mọi công thức hay đọc hết tài liệu tham khảo.

Theo yêu cầu cô, chạy lại code là điểm cộng, không bắt buộc; 30 trang là yêu cầu báo cáo chung của nhóm. Trước checkpoint này, ưu tiên hiểu và ghi chú theo template.

## 2. Kiến thức nền đủ để bắt đầu

| Thuật ngữ | Hiểu để đọc bài |
|---|---|
| LLM | Mô hình ngôn ngữ tạo truy vấn, xử lý thông tin, sinh câu trả lời. |
| RAG | Kết hợp lấy tài liệu bên ngoài với sinh câu trả lời. |
| Search agent | Thành phần lựa chọn bước suy luận và truy vấn tiếp theo, hoặc trả lời. |
| Retriever | Thành phần nhận truy vấn và lấy những đoạn văn được xếp hạng cao từ kho tài liệu. |
| Query / passage / corpus | Truy vấn / đoạn văn / kho tài liệu. |
| Multi-hop QA | Hỏi đáp cần nối nhiều mảnh bằng chứng. |
| Trajectory | Chuỗi bước suy luận, truy vấn, tài liệu nhận được và đáp án trong một lần xử lý. |
| Relevance / utility | Liên quan đến truy vấn / hữu ích cho nhiệm vụ trả lời. Hai khái niệm cần phân biệt. |
| Positive / negative | Đoạn được chọn làm mẫu ưu tiên / mẫu đối chiếu trong học tương phản; negative không mặc nhiên là thông tin sai. |
| Contrastive learning | Huấn luyện mô hình cho đầu vào gần mẫu positive hơn các negative trong không gian biểu diễn. |
| RL / reward | Học tăng cường / tín hiệu thưởng cho hành vi của agent. |
| Baseline / ablation | Phương pháp đối chiếu / thử bỏ hoặc thay một thành phần để xem đóng góp của nó. |
| EM | Exact Match: kiểm tra đáp án khớp đáp án chuẩn theo cách chuẩn hóa của bộ đánh giá. |

Ví dụ tự dựng, không phải kết quả thực nghiệm: cần tìm năm sinh của người X. Một đoạn kể sự nghiệp của X có thể rất giống truy vấn nhưng không cung cấp năm sinh. Một đoạn ít từ khóa hơn lại nêu đúng ngày sinh. Hãy dùng ví dụ này để phân biệt relevance với thông tin thực sự cần cho câu trả lời; sau đó đối chiếu case thật ở Table 6, trang PDF 16.

Lưu ý cho người không mạnh tiếng Anh (tránh bị trừ điểm nặng theo yêu cầu của cô): được dùng AI giải nghĩa để **đọc hiểu**, nhưng **tuyệt đối không dịch thô từng chữ rồi dán vào phiếu/báo cáo**. Đặc biệt tránh các lỗi dịch ngang nghĩa sau:
- *Passage utility* → viết là **độ hữu ích của đoạn văn** (không dịch *"tiện ích đoạn văn"*).
- *Positive / negative passages* → viết là **mẫu dương / mẫu âm** hoặc **đoạn văn dương / đoạn văn âm** (không dịch *"đoạn văn tích cực / tiêu cực"*).
- *Gold answer* → viết là **đáp án chuẩn** (không dịch *"câu trả lời vàng"*).
- *Off-the-shelf retriever* → viết là **bộ truy xuất có sẵn** (không dịch *"bộ truy xuất trên kệ"*).
- *In-batch / cross-device negatives* → viết là **mẫu âm trong cùng batch / khác GPU** (không dịch *"âm tính trong lô"*).
- *Exact Match (EM)* → viết là **độ đo khớp chính xác** (không dịch *"trận đấu chính xác"*).
- *Ablation study* → viết là **thực nghiệm phân tích/lược bỏ thành phần** (không dịch cụt là *"nghiên cứu cắt bỏ"*).

## 3. Lịch hoàn thành gói gọn trong 2 ngày (18/11 – 19/11)

Tổng thời lượng thực chất khoảng **7,5–9 giờ** (chia thành 4 phiên, điền phiếu **cuốn chiếu** ngay sau mỗi lượt để không dồn sang Thứ Sáu 20/11). Nội dung cốt lõi chỉ nằm ở **trang PDF 1–9**; trang 9–12 là tài liệu tham khảo và trang 13–19 là phụ lục/prompt chỉ mở ra tra cứu khi cần.

| Phiên học | Thời lượng | Nội dung đọc (theo trang PDF) | Sản phẩm chốt ngay vào [PHIEU_DOC_AGENTIC_R.md](PHIEU_DOC_AGENTIC_R.md) |
|---|---:|---|---|
| **Phiên 1 — Chiều T4 18/11**<br>*(Lượt 1: Câu chuyện)* | 1–1,5 giờ | Thuật ngữ nền; Abstract, §1, Figure 1 (trang 1–2); §3 (trang 3); nhìn tổng thể Figure 2 (trang 4); lướt Conclusion & Limitations (trang 8–9) và ví dụ Table 6 (trang 16). | Trả lời bằng lời mình 5 câu hỏi Lượt 1; **điền xong Mục 0 (3 ý đầu) và Mục 1**. |
| **Phiên 2 — Tối T4 18/11**<br>*(Lượt 2: Cơ chế & Train)* | 2–2,5 giờ | §4.1–4.2 (trang 3–6), Figure 2 (trang 4), Algorithm 1 (trang 6); tra nhanh thông số huấn luyện ở Appendix B (trang 13). | Tự phác/mô tả hai sơ đồ (lúc trả lời câu hỏi mới vs lúc huấn luyện); **điền xong Mục 2 và Mục 3**. |
| **Phiên 3 — Sáng/Chiều T5 19/11**<br>*(Lượt 3: Thực nghiệm)* | 2–2,5 giờ | Đọc §5.1 (trang 6) trước; sau đó đọc Table 1 (trang 7), Table 2 & Figures 3–4 (trang 8), Limitations (trang 9); tra nhanh Appendix A (trang 13) và kết luận chính ở Appendix C (trang 14–15). | Lập bảng kết quả ngắn + bảng ablation đúng cặp đối chiếu + 1 ngoại lệ; **điền xong nốt Mục 0, Mục 4 và Mục 5**. |
| **Phiên 4 — Tối T5 19/11**<br>*(Liên kết & Chốt bài)* | 1,5–2 giờ | Đối chiếu Search-R1 và chuỗi ReAct/IRCoT/FLARE dựa trên §2, §4.2, Appendix B; rà soát câu chữ tiếng Việt tự nhiên, tích checklist Mục 8 và tập giảng miệng 5 phút. | **Điền xong Mục 6, Mục 7–8** và hoàn tất bản nháp cá nhân ngay tối 19/11. *(T6 20/11 trống lịch; trước 12h T7 21/11 chỉ gửi nhóm/trao đổi nhanh với bạn đọc Search-R1).* |

Nguyên tắc cắt gọn để chắc chắn kịp 2 ngày: nắm thật chắc phần thân bài (**trang 1–9**). Với **Appendix C** (đổi backbone ở Table 3, thử nối lịch sử query ở Table 5) và **Figures 5–8** (prompt mẫu, trang 17–19), chỉ lấy kết luận chính trong 5–10 phút, không ngồi dịch từng câu.

## 4. Đọc ba lượt, mỗi lượt có sản phẩm

### Lượt 1: Nắm câu chuyện, 45–60 phút

Thứ tự: Abstract → Introduction → Figure 1 → §3 → Figure 2 (chỉ nhìn tổng thể) → Conclusion và Limitations.

Chưa giải từng ký hiệu. Với đoạn khó, ghi dấu hỏi và đọc tiếp. Đóng PDF rồi trả lời:

1. Agent và retriever làm hai công việc gì?
2. Vì sao một đoạn liên quan đến query chưa chắc giúp trả lời câu hỏi ban đầu?
3. Tại sao query của agent khác câu hỏi do người dùng nhập ban đầu?
4. Bài này thay đổi phần nào so với dùng một retriever có sẵn?
5. Cần kiểm tra bằng chứng nào trước khi tin các ưu điểm tác giả nêu?

Không trả lời được câu 1–2 thì quay lại §3 và ví dụ; chưa chuyển sang đọc công thức. Trả lời xong, điền ngay **Mục 0 (3 ý đầu) và Mục 1** của [PHIEU_DOC_AGENTIC_R.md](PHIEU_DOC_AGENTIC_R.md).

### Lượt 2: Hiểu cơ chế, 2–3 giờ

Đọc §4 theo câu hỏi, dùng Figure 2 và Algorithm 1 làm bản đồ. Các vị trí dưới đây theo số trang PDF, không phải số trang kỷ yếu 15987–16005.

| Chỗ đọc | Câu hỏi phải tự giải thích |
|---|---|
| §3, PDF 3 | Một lượt search bắt đầu thế nào, passage quay về đâu, agent dừng khi nào? |
| §4.1.1, PDF 3–5 | Trajectory sinh ra từ đâu? Local relevance và global answer correctness được xác định thế nào? |
| Figure 2, PDF 4 | Phần trên tạo supervision gì? Phần dưới cập nhật mô hình nào? |
| §4.1.1, PDF 5 | Xếp hạng hai tín hiệu theo thứ tự nào? Khi nào loại một mẫu training? |
| §4.1.2, PDF 5 | Input retriever chứa gì? Positive/negative dùng trong contrastive loss ra sao? |
| §4.2, PDF 5–6 | Agent học bằng gì? Retriever học bằng gì? Mỗi giai đoạn giữ cố định thành phần nào? |
| Algorithm 1, PDF 6 | Tự kể lại một vòng tối ưu, từ retriever vòng trước đến cặp agent/retriever vòng mới. |

Ba phân biệt quan trọng:

- **Lúc huấn luyện và lúc sử dụng:** đáp án chuẩn được dùng để tạo tín hiệu học; đừng vẽ như hệ thống cần biết đáp án chuẩn khi trả lời câu hỏi mới.
- **Hai kiểu lặp:** nhiều lượt tìm kiếm trong một câu hỏi khác với nhiều vòng huấn luyện agent–retriever.
- **Hai đối tượng học:** trọng tâm là retriever, nhưng framework cũng huấn luyện agent bằng RL. Không ghi “chỉ train retriever” hoặc “retriever được train bằng PPO”.

Cách đọc công thức: xác định đầu vào, đầu ra, ý nghĩa từng ký hiệu, rồi diễn đạt điều công thức khuyến khích. Chỉ cần giải thích được Eq. (1)–(3) đo gì, Eq. (4) ghép input gì, Eq. (5) làm positive được ưu tiên thế nào. Chưa cần tự chứng minh PPO. Xong lượt này, điền ngay **Mục 2 và Mục 3** của [PHIEU_DOC_AGENTIC_R.md](PHIEU_DOC_AGENTIC_R.md) trong tối 18/11.

### Lượt 3: Kiểm tra bằng chứng, 2–3 giờ

1. Đọc §5.1 trước bảng: dữ liệu train/test, agent, retriever, kho Wikipedia, số đoạn và lượt search.
2. Đọc Table 1 theo từng khối agent. Không trộn số ở hai khối hoặc đổi dataset rồi kết luận thắng thua.
3. Chọn hai kết quả chính và ít nhất một trường hợp không tốt nhất. Ghi rõ điều kiện và dòng/cột.
4. Đọc Table 2 để kiểm tra hai tín hiệu và iterative training có ích không. Các dòng “w/o” cần so với đúng cấu hình gốc của chúng, không mặc nhiên so mọi dòng với mô hình cuối.
5. Đọc Figure 3 về số lượt search. Số lượt ít hơn chưa đủ để kết luận toàn bộ thời gian chạy hoặc tổng chi phí huấn luyện ít hơn.
6. Đọc Figure 4 để kiểm tra thêm vòng training có tiếp tục tốt hơn không. Tránh tổng quát hóa số vòng tốt nhất của một thiết lập thành quy luật chung.
7. Đọc Limitations, rồi thêm nhận xét riêng có căn cứ; phân biệt điều tác giả nêu và điều mình suy luận.

Đọc bảng luôn ghi bốn thứ: **so cái gì – giữ nguyên cái gì – đổi cái gì – đo bằng gì**. Xong lượt này, điền ngay **Mục 0 (2 ý cuối), Mục 4 và Mục 5** của [PHIEU_DOC_AGENTIC_R.md](PHIEU_DOC_AGENTIC_R.md).

## 5. Bám sáu mục của template nhóm

| Mục | Nguồn cần đọc | Sản phẩm mình cần viết |
|---|---|---|
| 1. Problem | §1–3, Figure 1 | Vấn đề, hạn chế phương pháp cũ, một ví dụ và vị trí trong Agentic Retrieval. |
| 2. Method | §4, Figure 2, Algorithm 1 | Input/output, thành phần, hai sơ đồ, ai quyết định query/dừng và phần nào được con người thiết kế. |
| 3. Training | §4.1.1–4.2, Appendix B | Tách một đoạn cho retriever và một đoạn cho agent: dữ liệu, tín hiệu, loss/reward, thứ tự cập nhật. |
| 4. Experiments | §5, Tables 1–2, Figures 3–4, Appendix A–B | Dataset/thiết lập/metric; bảng ngắn của mình; ablation; mức tăng và giới hạn kết luận. |
| 5. Strengths & Limitations | §5, Limitations | Mỗi điểm mạnh đi kèm bảng/hình. Hạn chế tác giả nêu và nhận xét mình bổ sung ghi riêng. |
| 6. Connections | §2, §4.2; trao đổi các bạn | Ưu tiên đối chiếu Search-R1 và vị trí của retriever trong vòng reasoning–retrieval. |

Vì cô yêu cầu phân tích mối liên hệ, phần cá nhân nên giúp nhóm giải thích một vấn đề chung: “Agent biết tìm chưa đủ; retriever còn phải trả bằng chứng có ích”. Bản cá nhân là đầu vào cho báo cáo chung, không phải ghép nguyên sáu bản tóm tắt thành sáu chương độc lập.

Để không bị trễ sang ngày 20/11 vì chờ nhóm: ngay tối 19/11 bạn có thể tự viết xong khung Mục 6 dựa trực tiếp vào **§2, §4.2 và Appendix B** của bài (nơi tác giả chỉ rõ Agentic-R kế thừa cách train agent bằng PPO + loss masking của Search-R1 và bổ sung nhánh huấn luyện retriever). Sau đó, trước mốc 12h 21/11, chỉ cần trao đổi ngắn với bạn đọc Search-R1 ba câu để khớp chéo: phần nào là hành vi agent; Agentic-R kế thừa cách train agent ra sao; supervision cho retriever bổ sung điều gì?

## 6. Phiên khởi động chiều nay (18/11): 60–75 phút (phù hợp cả khi yếu tiếng Anh)

Bạn không cần tự ngồi dịch từng câu tiếng Anh: hãy mở [Paper_06_Agentic_R_ACL2026.pdf](Paper_06_Agentic_R_ACL2026.pdf) chủ yếu để **nhìn sơ đồ, các thẻ `<think>`, `<search>`, `<information>`, `<answer>` và vị trí mục**, kết hợp bản giải nghĩa tiếng Việt từng đoạn:

- **0–10 phút:** Đọc bảng thuật ngữ ở Mục 2 (nhận mặt ~15 từ khóa tiếng Anh cốt lõi) và tự vẽ nháp `Câu hỏi Q → Search Agent ↔ Retriever (Wikipedia) → Đáp án A`.
- **10–25 phút:** Nắm ý chính của Abstract và §1 Introduction (trang 1–2): vì sao E5/BGE chỉ đo độ tương đồng ngữ nghĩa là chưa đủ, và 3 rào cản khiến cách train retriever một lượt cũ không áp thẳng sang nhiều lượt được.
- **25–40 phút:** Nhìn **Figure 1** (trang 1), **§3** (trang 3) và đối chiếu nhanh ví dụ thật ở **Table 6** (trang 16) để tự kể lại cách hệ thống tìm kiếm nhiều lượt.
- **40–50 phút:** Nhìn tổng thể **Figure 2** (trang 4) và lướt **Conclusion + Limitations** (trang 8–9) để nắm 2 đóng góp chính cùng 2 giới hạn tác giả tự nhận.
- **50–75 phút:** Đóng PDF, tự trả lời 5 câu hỏi Lượt 1 bằng lời nói tự nhiên và điền luôn **Mục 0 (3 ý đầu) + Mục 1** vào [PHIEU_DOC_AGENTIC_R.md](PHIEU_DOC_AGENTIC_R.md) trước khi sang Phiên 2 tối nay.

## 7. Ghi chú, viết báo cáo và dùng AI an toàn

Mỗi ý ghi theo dạng: **mình hiểu gì → nguồn trang/mục/bảng → câu hỏi hoặc giới hạn**. Dùng phiếu đi kèm để điền cuốn chiếu ngay sau mỗi phiên. Cuối mỗi phiên, giải thích miệng 2 phút không nhìn tài liệu; nếu vướng, biết ngay chỗ cần hỏi hoặc xem lại.

Cấu trúc một đoạn báo cáo: vấn đề → cơ chế → lý do hợp lý → bằng chứng → giới hạn. Trích dẫn bản gốc. Tách số liệu tác giả báo cáo khỏi số liệu nhóm tự chạy.

Quy trình 3 bước khi nhờ AI hỗ trợ dịch/giải thích để không vi phạm quy định của cô: (1) nhờ AI cắt nghĩa thoát ý từng mục/công thức/bảng và giữ nguyên từ khóa chuyên ngành gốc trong ngoặc; (2) đối chiếu lại vị trí trên PDF; (3) đóng phần giải thích và **tự viết lại bằng lời của mình**. Yêu cầu cô nhấn mạnh thuật ngữ đúng, trích dẫn thật và khả năng giải thích khi hỏi đáp.

Gợi ý tự hỏi đáp tối 19/11 (và ôn nhanh trước khi gửi nhóm):

- Vì sao relevance khác utility?
- Vì sao cần cả local và global signal?
- Gold answer xuất hiện ở đâu, có dùng khi inference không?
- Retriever học gì và agent học gì?
- Hai kiểu vòng lặp khác nhau thế nào?
- Bảng nào chứng minh điểm mình đang nói? Có ngoại lệ không?
- Ít lượt search hơn có đủ chứng minh nhanh/rẻ hơn không?
- Agentic-R bổ sung gì so với Search-R1?

Đạt yêu cầu khi bạn có thể giảng bằng ví dụ và chỉ đúng nguồn cho từng kết luận, kể cả khi còn một vài chi tiết chưa hiểu.
