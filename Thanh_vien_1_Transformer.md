# transformer_vi_syllable_autocomplete.ipynb — huy26ms23411@fsb.edu.vn
## Phụ trách: Bài toán dịch, tokenization, vocabulary và kiến trúc tổng thể

**Phạm vi:** Cell 0–9; Mục 1–4.

### Các nội dung cần comment
1. **Mục tiêu và cách chạy:** mô tả luồng văn bản → token → embedding/vị trí → encoder → decoder → xác suất → huấn luyện → sinh.
2. **Câu nguồn và bản dịch tham chiếu:** giải thích câu tiếng Việt, câu tiếng Anh đã chọn và các cụm diễn đạt tương ứng.
3. **Tokenization:**
   - Unicode NFC, lowercase, apostrophe và regex.
   - Vì sao ví dụ tách tiếng Việt theo khoảng trắng tạo ra âm tiết/token, không phải phân đoạn từ chuyên dụng.
   - Vì sao số token nguồn và đích không cần bằng nhau.
4. **Vocabulary và token đặc biệt:**
   - Hai vocabulary riêng cho nguồn và đích.
   - `<pad>`, `<unk>`, `<bos>`, `<eos>`.
   - `source_ids`, `decoder_ids`, `label_ids`.
   - Vì sao decoder input được dịch phải so với nhãn dự đoán.
5. **Kiến trúc tổng thể:** vai trò encoder memory và decoder prefix; phân biệt phần A minh họa NumPy với phần B Transformer PyTorch có tham số học được.

### Câu hỏi cần tự trả lời
- Token khác từ hoàn chỉnh như thế nào?
- Vì sao cần hai vocabulary riêng?
- `<bos>` và `<eos>` có nhiệm vụ gì?
- Vì sao decoder input và target labels lệch nhau một vị trí?
- Encoder và decoder đảm nhận nhiệm vụ gì?

### Đầu ra cần hoàn thành
Comment cell 0–9; có thể trình bày dữ liệu văn bản được chuyển thành ID như thế nào và luồng tổng thể của Transformer.
