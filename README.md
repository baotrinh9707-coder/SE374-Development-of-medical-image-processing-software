# Limited-Angle CT Reconstruction

Đồ án môn **SE374 — Phát triển phần mềm xử lý ảnh y khoa**. Nhóm đang khảo sát tài liệu và chuẩn bị proposal.

## Mục tiêu

Tái tạo ảnh CT 2D khi chỉ có phép chiếu trong một cung góc. Nhóm sẽ kiểm tra liệu một U-Net nhỏ được cung cấp thông tin về cung quét có giữ đúng các đường biên theo hướng khi gặp cung quét mới hay không. Ảnh đầu ra được hiệu chỉnh dựa trên các phép chiếu đã đo, rồi so sánh với FBP và tái tạo lặp dùng total variation (TV).

## Bố cục repo

- [`docs/PLAN.md`](docs/PLAN.md) — Bài toán, phương pháp đề xuất, thiết kế thí nghiệm và checklist tiến độ.
- [`papers/`](papers/) — Hai bài giảng viên gửi và tài liệu theo từng hướng nghiên cứu limited-angle CT.
