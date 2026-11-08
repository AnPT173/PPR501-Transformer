# transformer_vi_syllable_autocomplete.ipynb — Thành viên 3
## Phụ trách: Output, loss, hiện thực PyTorch và huấn luyện

**Phạm vi:** Cell 21–29; Mục 9–12.

### Các nội dung cần comment
1. **Từ vector decoder đến xác suất và loss:**
   - Output projection biến decoder representation thành logits theo vocabulary đích.
   - Softmax chuyển logits thành phân phối xác suất.
   - Cross-entropy/NLL đo sai khác giữa dự đoán và token mục tiêu.
2. **Tổng hợp kích thước:** giải thích shape của tensor và mục đích các `assert` trong phần A.
3. **Transformer PyTorch:** cấu hình `d_model`, số head, `d_ff`, số block; vai trò encoder block, decoder block và lớp mô hình.
4. **Teacher forcing và huấn luyện:**
   - Decoder nhận prefix đúng từ câu đích đã dịch phải.
   - Cross-entropy tính trên token mục tiêu.
   - Adam cập nhật tham số.
   - Thứ tự `zero_grad → forward → loss → backward → clip → step`.
   - Phân biệt `train()` và `eval()` nếu xuất hiện.
5. **Giải thích log huấn luyện:** loss theo epoch, token accuracy nếu có; lưu ý mô hình chỉ học từ một cặp câu.

### Câu hỏi cần tự trả lời
- Logits khác xác suất thế nào?
- Loss được tính dựa trên đầu ra và nhãn nào?
- Teacher forcing hoạt động ra sao?
- Gradient được tính và cập nhật theo trình tự nào?
- Vì sao phải clipping gradient?
- Việc học thuộc một câu có chứng minh mô hình dịch tổng quát tốt không?

### Đầu ra cần hoàn thành
Comment cell 21–29; có thể giải thích từ đầu ra decoder đến loss và một vòng cập nhật tham số.
