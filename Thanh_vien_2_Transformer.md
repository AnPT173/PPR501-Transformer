# transformer_vi_syllable_autocomplete.ipynb — Thành viên 2
## Phụ trách: Embedding, positional encoding và ba loại attention

**Phạm vi:** Cell 10–20; Mục 5–8.

### Các nội dung cần comment
1. **Embedding và positional encoding:** ánh xạ token ID thành vector; lý do cần thông tin vị trí; cách cộng embedding với positional encoding.
2. **Encoder self-attention:**
   - Q, K, V được tạo từ biểu diễn đầu vào.
   - Tính scaled dot-product scores, chia cho căn bậc hai của `d_k`.
   - Softmax tạo trọng số attention; nhân với Value để tổng hợp thông tin.
   - Đọc heatmap: query theo hàng, key theo cột; không coi attention là bằng chứng chắc chắn về ngữ nghĩa.
3. **Hoàn thành encoder:** residual connection, LayerNorm và FFN.
4. **Decoder masked self-attention:**
   - Causal/future mask và lý do chặn các token tương lai.
   - Vì sao mask được áp dụng trước softmax.
5. **Cross-attention:**
   - Query đến từ decoder.
   - Key/Value đến từ encoder memory.
   - Cách decoder dùng thông tin câu nguồn để dự đoán câu đích.

### Câu hỏi cần tự trả lời
- Vì sao Transformer cần positional encoding?
- Q, K, V có ý nghĩa gì?
- Vì sao scaled dot-product attention chia cho `sqrt(d_k)`?
- Residual, LayerNorm và FFN đóng vai trò gì?
- Causal mask ngăn decoder nhìn thấy điều gì?
- Cross-attention khác self-attention như thế nào?

### Đầu ra cần hoàn thành
Comment cell 10–20; có thể vẽ/diễn giải đường đi của tensor qua encoder self-attention, decoder masked self-attention và cross-attention.
