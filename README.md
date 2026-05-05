[Uploading README.md…]()
# ⚔️ Weapon Naming Tool v7 Pro

Công cụ dịch tên vũ khí & hội thoại NPC cho game, hỗ trợ **Tiếng Việt · Ả Rập · Hàn Quốc** — chạy thẳng trên trình duyệt, không cần cài đặt.

🔗 **[Mở Tool](https://magicalgnome721.github.io/weapon-naming-tool/)**

---

## 🚀 Cách sử dụng

### 1. Nhập API Key
Paste OpenAI API key vào ô **"Khóa API OpenAI"** → bấm **Test** để kiểm tra kết nối.  
Mô hình mặc định `gpt-4o-mini` — rẻ nhất, phù hợp batch lớn.

### 2. Chọn ngôn ngữ đích
Chọn một trong ba tab: 🇻🇳 Tiếng Việt · 🇸🇦 Ả Rập · 🇰🇷 Hàn Quốc  
Tool tự load prompt + glossary tương ứng.

### 3. Upload file
Kéo thả hoặc click vào vùng upload → chọn file `.xlsx` / `.csv` chứa cột text tiếng Anh cần dịch.  
Nếu file có nhiều cột, chọn đúng cột cần dịch ở dropdown bên dưới.

### 4. Thêm Glossary tùy chỉnh *(tùy chọn)*
Vào phần **Glossary Tùy Chỉnh** → điền thuật ngữ cố định (tên địa danh, nhân vật, kỹ năng...) → bấm **Thêm**.  
Glossary sẽ được ưu tiên áp dụng, LLM không được dịch khác đi.

### 5. Bấm Dịch
Bấm **Dịch → [ngôn ngữ]** — tool tự chia batch, gọi API và hiển thị kết quả real-time.  
Các dòng đã dịch được **cache lại** — chạy lại không tốn thêm API call.

### 6. Xuất kết quả
Bấm **Xuất Excel** → tải về file `.xlsx` gồm 3 cột:

| English | LLM Output | Post-Processed |
|---------|-----------|----------------|
| Text gốc | Bản dịch thô | Bản dịch đã qua post-process |

---

## 🏗️ Kiến trúc Pipeline

```
① Typo Fix → ② Global Glossary → ③ Lang Glossary → ④ Lang Prompt → ⑤ LLM → ⑥ Post-Process → ⑦ QA
```

| Bước | Mô tả |
|------|-------|
| ① Typo Fix | Tự động sửa lỗi chính tả phổ biến trong text gốc |
| ② Global Glossary | Áp glossary ngữ nghĩa chung (loại vũ khí, nguyên tố...) |
| ③ Lang Glossary | Áp glossary tùy chỉnh theo ngôn ngữ đích |
| ④ Lang Prompt | Inject system prompt phong cách phù hợp (kiếm hiệp / فصحى / MMO) |
| ⑤ LLM | Gọi OpenAI API dịch theo batch |
| ⑥ Post-Process | Rule-based fix sau LLM (khóa loại vũ khí, đại từ...) |
| ⑦ QA | Cảnh báo bản dịch dài 📏, trùng nhau ♊, mất placeholder ⚠ |

---

## ⚙️ Tùy chọn

| Option | Mô tả |
|--------|-------|
| **Cache** | Bỏ qua dòng đã dịch, tiết kiệm token |
| **Post-Process** | Áp rule cứng sau LLM (mặc định bật) |
| **Typo Auto-Fix** | Sửa lỗi input trước khi dịch |
| **Mô hình kép** | Dùng model mạnh hơn cho batch lỗi |
| **Batch Token Budget** | Điều chỉnh kích thước batch (1500 / 2500 / 4000 token) |

---

## 📝 Lưu ý

- API key chỉ gửi thẳng đến OpenAI, không lưu ở đâu khác
- Hỗ trợ placeholder: `%s` `%d` `{0}` `{1}` — được giữ nguyên hoàn toàn
- Hỗ trợ multi-part string phân cách bằng `|`
- Glossary có thể xuất/nhập dạng JSON để tái sử dụng
