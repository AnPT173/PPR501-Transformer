# transformer_vi_syllable_autocomplete.ipynb — Thành viên 4
## Phụ trách: Sinh câu, kiểm chứng, chẩn đoán, checkpoint và kết luận

**Phạm vi:** Cell 30–41; Mục 13–18.

### Các nội dung cần comment
1. **Greedy decoding:** bắt đầu từ `<bos>`, dự đoán token có xác suất cao nhất, nối vào prefix và lặp đến `<eos>` hoặc giới hạn độ dài; phân biệt với teacher forcing.
2. **Kiểm chứng và attention sau học:**
   - Cách chạy inference/đối chiếu bản dịch.
   - Token accuracy dưới teacher forcing và ý nghĩa giới hạn của nó.
   - Causal leakage test kiểm tra điều gì.
   - Cách đọc attention visualization sau huấn luyện.
3. **Thí nghiệm chẩn đoán:** giải thích các biến thể câu nguồn (nguồn gốc, đảo thứ tự âm tiết, toàn UNK, một token UNK); kết quả thay đổi/không thay đổi gợi ý điều gì.
   - Phải phân biệt quan sát thực tế và giả thuyết.
   - Không kết luận khả năng dịch tổng quát từ một cặp câu.
4. **Lưu checkpoint và nạp lại:**
   - `state_dict`, cấu hình, source/target vocabulary, seed, lịch sử train và dữ liệu tham chiếu.
   - Vì sao vocabulary phải được lưu cùng trọng số: ID phụ thuộc thứ tự token.
   - Luồng khôi phục mô hình và suy luận.
5. **Tổng hợp, thảo luận, kết luận và tài liệu:** giải thích training CE/PPL, cấu hình, kết quả sinh và giới hạn thực nghiệm.

### Câu hỏi cần tự trả lời
- Greedy decoding hoạt động thế nào?
- Token accuracy khác exact match thế nào?
- Causal leakage test phát hiện lỗi gì?
- Vì sao cần thử làm thay đổi câu nguồn?
- Vì sao phải lưu vocabulary cùng `state_dict`?
- Vì sao một cặp câu không đủ để đánh giá năng lực dịch?

### Đầu ra cần hoàn thành
Comment cell 30–41; chuẩn bị phần trình bày kết quả sinh, thí nghiệm chẩn đoán, cách lưu/nạp và giới hạn của mô hình.
