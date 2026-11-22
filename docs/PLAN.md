# Kế hoạch nghiên cứu

**Trạng thái:** Đang khảo sát tài liệu và soạn proposal. Các mốc dưới đây là đề xuất để nhóm thảo luận.

## Bài toán và giả thuyết

Trong sparse-view CT như hai bài giảng viên gửi, các góc đo thưa và trải trên toàn miền quét. Trong limited-angle CT, số đo chỉ nằm trong một cung liên tục, chẳng hạn 90° trong miền 180° của CT tia song song 2D. Khi xoay cung đo, các hướng biên khó khôi phục cũng thay đổi.

**Câu hỏi nghiên cứu:** Với cùng kiến trúc và dữ liệu huấn luyện, việc cho U-Net biết vị trí và độ rộng cung đo có cải thiện khả năng giữ biên theo hướng khi gặp cung mới không?

## Phương pháp đề xuất

1. Dùng **filtered back projection (FBP)** để tái tạo ảnh ban đầu từ các góc đã đo.
2. Dùng **U-Net nhỏ** để dự đoán phần hiệu chỉnh ảnh. Mạng nhận thông tin về vị trí và độ rộng cung đo.
3. Chiếu ảnh dự đoán về các góc đã đo và hiệu chỉnh dựa trên sai lệch với sinogram đầu vào (*data consistency*).

Bài Long-sequence modeling gợi ý cách học chi tiết cục bộ cùng cấu trúc dài hạn. CG-GLORE gợi ý cách dùng mô hình phép chiếu để cập nhật ảnh. Xem [hai bài giảng viên gửi và các bài liên quan](../papers/#giảng-viên-gửi).

## Thiết kế thí nghiệm

| Hạng mục | Thiết lập dự kiến |
| --- | --- |
| Dữ liệu | Khởi đầu bằng phantom có cấu trúc nhỏ theo nhiều hướng. Sau đó thử trên một tập con [LoDoPaB-CT](https://pmc.ncbi.nlm.nih.gov/articles/PMC8052416/) với sinogram mô phỏng. Chia tập theo bệnh nhân khi dùng dữ liệu CT. |
| Cung quét | Huấn luyện với cung 60° và 120° ở một số vị trí. Kiểm tra riêng vị trí cung chưa gặp và độ rộng 90° chưa dùng trong huấn luyện. Giữ cùng số phép chiếu khi so các vị trí của cùng độ rộng. |
| Baseline | FBP và tái tạo lặp bằng total variation (TV). |
| Kiểm tra từng thành phần | Giữ cùng kiến trúc và cách chia dữ liệu. So bốn cấu hình U-Net khi bật hoặc tắt thông tin cung quét và bước hiệu chỉnh theo số đo. |
| Chỉ số | PSNR, SSIM, sai số chiếu lại ở góc đã đo và F1 của đường biên theo nhóm hướng trên phantom. |
| Minh họa | So ảnh khi xoay cung đo, phóng to cấu trúc nhỏ và đánh dấu biên bị mất hoặc biên giả trên phantom. |

Các ảnh có độ khớp tương tự ở góc đã đo vẫn có thể khác nhau ở các biên khó quan sát. Nhóm sẽ đọc sai số phép chiếu cùng với chỉ số biên và ảnh tham chiếu. [Learning the Invisible](https://doi.org/10.1088/1361-6420/ab10ca)

## Tiến độ

- [x] Khảo sát hai bài giảng viên gửi và các hướng limited-angle CT liên quan.
- [ ] Chốt câu hỏi và thiết lập thí nghiệm trong proposal.
- [ ] Tạo sinogram giới hạn góc và chạy baseline FBP, TV.
- [ ] Huấn luyện các biến thể U-Net và kiểm tra trên cung mới.
- [ ] Tổng hợp chỉ số và phân tích các ca tái tạo lỗi.
- [ ] Hoàn thiện report và demo.

## Nhật ký quyết định

| Trạng thái | Quyết định | Lý do |
| --- | --- | --- |
| Đề xuất | Bắt đầu với hình học tia song song 2D. | Dễ kiểm soát vị trí, độ rộng và số phép chiếu khi so sánh. |
| Đề xuất | Dùng U-Net nhỏ làm mô hình chính. | Giữ chi phí huấn luyện thấp để chạy đủ bốn cấu hình đối chứng. |
| Đề xuất | Tách bài kiểm tra vị trí cung mới khỏi độ rộng cung mới. | Đo riêng khả năng tổng quát hóa theo vị trí và theo độ rộng. |
