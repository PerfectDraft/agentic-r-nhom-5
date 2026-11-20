# Bài tập lớn: Agentic RAG / Agentic Search

Cập nhật ngày 22/10/2026. Đây là bản nắm yêu cầu và định hướng ban đầu, chưa phải báo cáo hoặc kết quả nghiên cứu của nhóm.

## 1. Nguồn và mức độ xác nhận

- Người dùng xác nhận nhóm có 5 người, chọn chủ đề Agentic RAG / Agentic Search, phải đọc paper và làm slide thuyết trình, báo cáo.
- Ảnh danh sách nhóm: Đào Văn Huân, Hùng Phan, Ngọc Mai, Nguyễn Ngọc Ánh, Phạm My. Chưa xác nhận người dùng tương ứng với tên nào và vai trò từng người.
- Ghi âm: `D:/Downloads/20261015_165524.m4a`, dài khoảng 10 phút 29 giây. Đã xử lý bằng nhận dạng tiếng Việt cục bộ; có nhiều đoạn nhỏ tiếng/nhiễu và lỗi nhận dạng. Nội dung bên dưới là diễn giải, không phải trích nguyên văn lời cô.
- [Bảng cô cung cấp](https://docs.google.com/spreadsheets/d/196oE76vS1VhdpKABedS18KKUXDg2vZH_/edit?gid=1132376818#gid=1132376818): đọc trực tiếp trong trình duyệt, tab `Final`, hàng 7, ô F7:K7. Bảng là file Excel mở trên Google Sheets. Kết nối Drive không tải được nội dung; trình duyệt đọc được.
- Trong phiên bản bảng đang hiển thị, topic này có STT 5, khác số 4 người dùng nêu. Đối chiếu theo tên chủ đề; không suy ra số nhóm chính thức từ STT trong bảng.
- Đã đối chiếu tên và đọc abstract của các paper qua nguồn tác giả/nhà xuất bản. Chưa đọc kỹ toàn văn, kiểm tra thí nghiệm, hoặc chạy code.

## 2. Các ý quan trọng từ ghi âm

| Mốc gần đúng | Diễn giải | Hệ quả khi làm bài |
| --- | --- | --- |
| 00:10–00:30 | Có thể chọn paper khác, nhưng phải bảo đảm uy tín và tính phù hợp/cập nhật. | Danh sách là gợi ý; không tự thay bằng bài cũ, kém liên quan. |
| 00:37–00:53 | Mọi người gần như đều phải đọc survey để hiểu bài toán và xu hướng. | Cả 5 người cùng đọc survey trước khi chia phần chuyên sâu. |
| 00:54–01:34 | Có thể chọn ít bài hơn, đọc sâu một hướng hoặc mở rộng bằng bài khác; cô không bắt buộc dùng đúng toàn bộ gợi ý. | Không mặc định phải trình bày hết 6 bài. Chọn phạm vi theo sức nhóm. |
| 01:40–01:52 | Trình bày và hỏi đáp có đánh giá cá nhân. | Mỗi người cần hiểu phần mình và mối liên hệ với bài chung. |
| 01:52–02:28 | Ưu tiên bài có source code; chạy lại được là điểm cộng. Cô không bảo đảm mọi bài gợi ý đều có code. | Có thể cân nhắc thực nghiệm; chưa có cơ sở coi tái lập mọi paper là yêu cầu bắt buộc. |
| 07:33–08:33 | Cần kết nối các bài, chắt lọc điều muốn dạy/chia sẻ với lớp; không kể lần lượt toàn bộ từng paper. | Slide và báo cáo phải có câu hỏi trung tâm, so sánh và kết luận của nhóm. |
| 08:35–09:24 | Survey dùng để đưa định nghĩa, bức tranh tổng quan và dẫn vào các hướng cụ thể. | Không dùng phần lớn thời gian để kể lại toàn bộ survey. |
| 09:24–09:55 | Cô phản đối việc đưa PDF cho AI diễn giải rồi nộp báo cáo rất dài; muốn thấy nhóm học và tiếp thu được gì. | Viết có chọn lọc, dẫn nguồn và tự kiểm tra lập luận. |
| 10:04–10:10 | Thuyết trình vào những tuần cuối, sau phần lý thuyết. | Chưa xác định ngày cụ thể. |

### Chưa chốt từ nguồn hiện có

- Deadline và ngày thuyết trình cụ thể; nơi nộp và quy tắc đặt tên.
- Khoảng 07:06–07:18 có đề cập thời lượng trình bày, nhận dạng được cụm “15 phút” nhưng phần xung quanh lỗi. Tạm dùng 15 phút để thử xây bố cục nếu cần; phải xác nhận trước khi chốt slide.
- Khoảng 04:08–04:22 có trao đổi về report và cuối kỳ, nhưng nhận dạng chưa đủ rõ để chốt hạn nộp hoặc hình thức báo cáo cá nhân/nhóm.
- Độ dài báo cáo, số slide, rubric, quy định số người thuyết trình và yêu cầu demo cụ thể.

## 3. Sáu paper gợi ý đúng hàng chủ đề

Các mô tả dưới đây chỉ phản ánh abstract và vai trò dự kiến khi đọc, chưa phải đánh giá chất lượng hoặc kết luận thực nghiệm của nhóm.

| Vai trò trong bảng | Paper và nguồn | Câu hỏi chính khi đọc |
| --- | --- | --- |
| Survey / Overview | Deng et al. **Data-Centric Perspectives on Agentic Retrieval-Augmented Generation: A Survey**. Findings of ACL, 2026. [Nguồn](https://aclanthology.org/2026.findings-acl.78/) | Dữ liệu, tác vụ và đánh giá Agentic RAG khác RAG thông thường thế nào? Survey tập trung vào góc nhìn dữ liệu. |
| Foundation | Yao et al. **ReAct: Synergizing Reasoning and Acting in Language Models**. ICLR, 2023. [Nguồn](https://arxiv.org/abs/2210.03629) | Việc xen kẽ suy luận và hành động/công cụ giúp cập nhật thông tin ra sao? Phạm vi ReAct rộng hơn riêng RAG. |
| Improvement | Trivedi et al. **Interleaving Retrieval with Chain-of-Thought Reasoning for Knowledge-Intensive Multi-Step Questions** — IRCoT. ACL, 2023. [Nguồn](https://aclanthology.org/2023.acl-long.557/) | Vì sao câu hỏi nhiều bước cần xen kẽ truy xuất và suy luận? |
| Improvement | Jiang et al. **Active Retrieval Augmented Generation** — FLARE. EMNLP, 2023. [Nguồn](https://aclanthology.org/2023.emnlp-main.495/) | Khi nào cần truy xuất thêm, và nên tìm gì trong quá trình sinh văn bản? |
| Emerging direction / SOTA | Jin et al. **Search-R1: Training LLMs to Reason and Leverage Search Engines with Reinforcement Learning**. COLM, 2025. [Nguồn bản hội nghị](https://openreview.net/pdf?id=Rwhi91ideu), [arXiv](https://arxiv.org/abs/2503.09516) | Có thể dùng học tăng cường để mô hình học cách tìm kiếm nhiều lượt như thế nào? |
| Emerging direction / SOTA | Liu et al. **Agentic-R: Learning to Retrieve for Agentic Search**. Findings of ACL, 2026. [Nguồn](https://aclanthology.org/2026.findings-acl.785/) | Huấn luyện bộ truy xuất theo truy vấn và kết quả cuối của tác tử như thế nào? |

“Emerging direction / SOTA” là nhãn cột trong bảng, không phải kết luận rằng các bài này đang tốt nhất trên mọi tác vụ hoặc ở hiện tại.

## 4. Mạch nội dung đề xuất

Đây là đề xuất tổ chức của trợ lý, không phải yêu cầu nguyên văn từ giảng viên.

**Câu hỏi trung tâm:** Khi nào và bằng cách nào một hệ thống cần tìm thêm thông tin để trả lời tốt hơn?

1. Bài toán và ví dụ dùng xuyên suốt: một câu hỏi cần kết nối thông tin từ nhiều nguồn.
2. RAG truy xuất một lần và giới hạn; dùng survey để đặt bức tranh tổng quan và bài toán dữ liệu.
3. ReAct: nền tảng phối hợp suy luận với hành động/công cụ.
4. IRCoT và FLARE: hai cách điều khiển truy xuất. IRCoT tập trung vào câu hỏi nhiều bước; FLARE tập trung vào truy xuất chủ động trong sinh văn bản. Không coi hai bài là cùng một thiết lập thí nghiệm.
5. Search-R1 và Agentic-R: học chính sách tìm kiếm ở phía mô hình/tác tử và học bộ truy xuất phù hợp với tìm kiếm nhiều lượt. Không mặc định bài sau là phiên bản nối tiếp trực tiếp của bài trước.
6. So sánh, hạn chế, dữ liệu và đánh giá; nhóm rút ra điều gì, khi nào cách phức tạp hơn đáng dùng?

Không so trực tiếp các con số từ những paper dùng khác dataset, mô hình, corpus hoặc ngân sách truy xuất.

## 5. Cách làm việc cho nhóm 5 người

- Cả 5 cùng đọc survey và thống nhất thuật ngữ, bài toán, ví dụ chung.
- Có thể giao 5 paper kỹ thuật cho 5 người làm đầu mối. Đầu mối không đồng nghĩa chỉ người đó cần hiểu bài: mỗi bài cần thêm một người đọc chéo, và cả nhóm cần hiểu ý chính.
- Mỗi người bàn giao cùng một mẫu: bài toán; ý tưởng; sơ đồ hoạt động; dữ liệu và thiết lập đánh giá; kết quả có nguồn bảng/hình; hạn chế; liên hệ với các bài khác.
- Sau vòng đọc, chọn bài nào đi sâu, bài nào chỉ dùng đối chiếu. Không bắt buộc đưa cả 6 bài vào slide với dung lượng ngang nhau.
- Chốt một đề cương chung cho báo cáo và slide trước khi viết riêng. Mỗi người viết phần phụ trách, cùng rà soát liên kết và kết luận; tránh dồn toàn bộ khâu tổng hợp cho một người.
- Nếu thử code, tách rõ demo minh họa nguyên lý và tái lập thí nghiệm paper. Chưa chọn demo hoặc cam kết tái lập trước khi kiểm tra code, dữ liệu và tài nguyên.
- Chưa gán tên cụ thể, deadline nội bộ hoặc tuyên bố ai đã hoàn thành việc gì.

## 6. Việc tiếp theo

- [ ] Cả nhóm xác nhận deadline, thời lượng, đầu ra và cách nộp qua thông báo lớp/giảng viên.
- [ ] Thống nhất mức hiểu nền tảng và khả năng dành thời gian của từng người.
- [ ] Đọc chung survey, tạo bảng ghi chú so sánh, phân đầu mối và người đọc chéo.
- [ ] Đọc sâu rồi chốt phạm vi, đề cương báo cáo và slide.
- [ ] Kiểm tra khả năng làm demo nếu nhóm muốn lấy thêm bằng chứng thực nghiệm.

## 7. Tệp phục vụ đối chiếu

- Bản chép lời tự động: `../tmp/ghi_am_btl_20261015/transcript.txt`.
- Bản kiểm tra lại một số đoạn sau tăng rõ tiếng: `../tmp/ghi_am_btl_20261015/recheck.txt`.
- Cả hai bản có lỗi nhận dạng và các câu lặp không đáng tin ở đoạn nhiễu/nhỏ tiếng; không dùng nguyên văn để trích lời cô. Khi cần chốt yêu cầu còn mơ hồ, đối chiếu lại ghi âm gốc hoặc thông báo lớp.
