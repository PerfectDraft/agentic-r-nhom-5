# Danh mục tài liệu — nhóm 5, bài 6 Agentic-R

Kiểm kê local ngày **18/11/2026**. Các bản tải Google/ACL đã có từ phiên 17/11; lần kiểm kê này không đồng nghĩa đã tải lại bản online. Gói này tập hợp tài liệu cho nhiệm vụ, không phải bộ dữ liệu hay môi trường chạy lại paper.

## 1. Thứ tự ưu tiên khi nguồn khác nhau

- Phân công cá nhân: lời người dùng sửa trực tiếp và ảnh sheet K7 → template/đề cương nội bộ.
- Yêu cầu học phần: tài liệu cô hiện hành → kế hoạch nhóm → ghi chú lịch sử tháng 10.
- Nội dung kỹ thuật: PDF tác giả/nhà xuất bản và code tác giả → trích xuất text → hướng dẫn của trợ lý.
- Tiến độ: file hiện tại và xác nhận người dùng → kế hoạch dự kiến. Kế hoạch không chứng minh việc đã hoàn thành.

## 2. File làm việc và nguồn chính

| File | Vai trò | Trạng thái / lưu ý |
|---|---|---|
| [AGENTS.md](AGENTS.md) | Hướng dẫn agent tiếp nhận | Quy tắc tương đối ổn định. |
| [HANDOFF.md](HANDOFF.md) | Tiến độ, hạn, bước tiếp, prompt bàn giao | Cập nhật sau mỗi lượt thay đổi có ý nghĩa. |
| [HUONG_DAN_DOC_AGENTIC_R.md](HUONG_DAN_DOC_AGENTIC_R.md) | Kế hoạch và phương pháp đọc cho người mới | Tạo 17/11; lịch chưa phải tiến độ hoàn thành. |
| [PHIEU_DOC_AGENTIC_R.md](PHIEU_DOC_AGENTIC_R.md) | Phiếu sáu mục theo template | Nơi điền ghi chú theo từng lượt đọc. |
| [Paper_06_Agentic_R_ACL2026.pdf](Paper_06_Agentic_R_ACL2026.pdf) | Paper chính, bản ACL 19 trang | Nguồn để trích dẫn và kiểm chứng. |
| [yeu_cau_cua_co.txt](nguon_tham_khao/yeu_cau_cua_co.txt) | Yêu cầu chính thức, bản TXT xuất từ Google Docs | 20 phút + 10 phút QA; code không bắt buộc; báo cáo chung tiếng Việt, TNR 13, giãn dòng 1.3, tối thiểu 30 trang nội dung. |
| [template_nhom.txt](nguon_tham_khao/template_nhom.txt) | Sáu mục và câu hỏi đọc paper của nhóm | Đánh số nội bộ khác sheet; hạn trong bản này 12h 21/11. |
| [Ke_hoach_BTL_KPDL_Agentic_Retrieval.docx](nguon_tham_khao/Ke_hoach_BTL_KPDL_Agentic_Retrieval.docx) | Đề cương, phân công và ý tưởng thực nghiệm nhóm | Là kế hoạch; không coi các nội dung đề xuất là code/kết quả đã có. |
| [agentic_r_text.txt](nguon_tham_khao/agentic_r_text.txt) | Text trích xuất PDF | Có marker trang; công thức/layout cần đối chiếu PDF. |

## 3. Bằng chứng người dùng gửi, đã chép vào dự án

| File | Ý nghĩa | Nguồn |
|---|---|---|
| [anh_phan_cong_nhom5_bai6.png](nguon_tham_khao/bang_chung/anh_phan_cong_nhom5_bai6.png) | Hàng Agentic RAG / Agentic Search, cột 6: Agentic-R; nhãn Emerging direction/SOTA | Ảnh người dùng gửi khi sửa nhận diện paper. |
| [anh_thong_bao_deadline_cu.jpg](nguon_tham_khao/bang_chung/anh_thong_bao_deadline_cu.jpg) | Ảnh ban đầu ghi 27/11, khác template hiện tại | Giữ làm bằng chứng xung đột; không tự lấy thay mốc 21/11. |

Không phụ thuộc đường dẫn Temp của hai ảnh gốc để đọc bộ bàn giao.

## 4. Bổ trợ và lịch sử

| File | Vai trò | Giới hạn |
|---|---|---|
| [Tai_lieu_bo_tro_Data_Centric_Survey.pdf](nguon_tham_khao/Tai_lieu_bo_tro_Data_Centric_Survey.pdf) | Survey cùng chủ đề | Không phải bài cá nhân số 6. |
| [data_centric_survey_text.txt](nguon_tham_khao/data_centric_survey_text.txt) | Text survey để tra cứu | Không nhầm với text Agentic-R. |
| [BTL_Agentic_RAG_Context_2026-10-22.md](nguon_tham_khao/lich_su/BTL_Agentic_RAG_Context_2026-10-22.md) | Bản sao bối cảnh từ `Tong_hop/BTL_Agentic_RAG_Context.md` | Nguồn tháng 10, có thông tin cũ; các đường dẫn tương đối bên trong phản ánh vị trí cũ và có thể không mở trong gói. Không đọc các liên kết đó để suy ra có file đi kèm. |
| [Note_bai_giua_ky_KPDL_2026-10-22.md](nguon_tham_khao/lich_su/Note_bai_giua_ky_KPDL_2026-10-22.md) | Bản sao ghi chú yêu cầu ban đầu | Chưa có đề chính thức ở thời điểm ghi; có phần Telecom không thuộc nhiệm vụ Agentic-R. Đường dẫn lịch sử có thể không có trong gói. |
| [Figure 2, trang PDF 4](hinh_minh_hoa/agentic_r_page_4.png) | Render phương pháp để đọc nhanh | Bản render từ PDF, không phải sơ đồ nhóm tự thiết kế. |
| [Table 1, trang PDF 7](hinh_minh_hoa/agentic_r_page_7.png) | Render kết quả chính | Giữ điều kiện agent/dataset khi lấy số. |
| [Table 2 và Figures 3–4, trang PDF 8](hinh_minh_hoa/agentic_r_page_8.png) | Render ablation và số lượt tìm kiếm | Không đồng nhất search turns với latency. |

Các file gốc trong `Tong_hop/` được giữ nguyên. Không cần mang slide các chương, quiz, notebook và CSV Telecom vào gói paper 6.

## 5. Nguồn online và định danh

| Nguồn | Link / định danh | Dùng để |
|---|---|---|
| Drive nhóm | https://drive.google.com/drive/folders/1JYV5n4-CX4DeKVpwuTZxlPZUqqxpM_hs | Đề cương và template nhóm. |
| Danh sách cô | https://docs.google.com/spreadsheets/d/196oE76vS1VhdpKABedS18KKUXDg2vZH_/edit?gid=1132376818#gid=1132376818 | Tab Final, F7:K7; bài cá nhân ở K7. |
| Yêu cầu cô | https://docs.google.com/document/d/1uIi71u2jV41U7B3B03N7B4BDJ5U89-cvbUdlaacbGYo/edit | Nguồn chính thức học phần. |
| Template nhóm | https://docs.google.com/document/d/1G3k18IhIkDxbX8GoLGKHCK80EJ1LCVAj6o3uyw1_PQ0/edit | Sáu mục và phân công nội bộ. |
| Đề cương nhóm | https://drive.google.com/file/d/19x4R0Dg6jZ1Md37TIGgpAtlImVLJg_m0/view | File DOCX đã tải. |
| Agentic-R bản hội nghị | https://aclanthology.org/2026.findings-acl.785/ | Metadata và PDF chính thức. |
| Agentic-R PDF | https://aclanthology.org/2026.findings-acl.785.pdf | Bản dùng trong gói. |
| Agentic-R arXiv | https://arxiv.org/abs/2601.11888 | Bản tiền công bố; nội dung/vị trí có thể khác bản ACL. |
| Code Agentic-R | https://github.com/8421BCD/Agentic-R | Code tác giả; chưa clone hoặc chạy tại workspace này. |

Thứ tự sáu bài trên sheet của cô:

1. Data-Centric Survey — https://aclanthology.org/2026.findings-acl.78/
2. ReAct — https://arxiv.org/abs/2210.03629
3. IRCoT — https://aclanthology.org/2023.acl-long.557/
4. FLARE — https://aclanthology.org/2023.emnlp-main.495/
5. Search-R1 — https://arxiv.org/abs/2503.09516
6. **Agentic-R** — https://aclanthology.org/2026.findings-acl.785/

Chỉ Agentic-R và survey đã có PDF trong bộ local; không ghi đã tải bốn bài còn lại. Liên hệ Search-R1 là hướng ưu tiên khi so sánh, không phải kết luận đã chạy kết hợp.

## 6. File không phải tài liệu học và gói chuyển máy

Trong nguồn cũ còn `drive_folder.html`, `sheet_download_bi_han_che.html`, `sheet_export_bi_han_che.html`: listing Drive hoặc trang lỗi truy cập/export. Giữ nguyên tại máy để chẩn đoán; loại khỏi ZIP và không dùng làm nội dung spreadsheet.

`tmp/` chứa render làm việc cũ, gồm cả survey. Những hình Agentic-R cần dùng đã được chép sang `hinh_minh_hoa/`; không đóng gói tmp.

Thư mục `handoff/` có ZIP và manifest JSON liệt kê đường dẫn tương đối, kích thước, SHA-256 của file được đóng gói. ZIP gồm AGENTS ở gốc cùng thư mục Bao_so_6. Giải nén rồi mở AGENTS; hoặc chỉ mở Bao_so_6/AGENTS.md để tiếp tục nhiệm vụ. Đây là snapshot **18/11/2026**, không tự đồng bộ khi ghi chú thay đổi.
