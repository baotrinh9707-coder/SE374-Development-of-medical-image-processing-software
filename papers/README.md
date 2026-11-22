# Tài liệu tham khảo

## Giảng viên gửi

| Bài | Ý tưởng dùng cho đồ án |
| --- | --- |
| Bui, Le & Nguyen (2026). [Long-sequence modeling for sparse-view computed tomography reconstruction](https://link.springer.com/article/10.1007/s00138-026-01901-1) | Dùng token 2×2 và mô hình chuỗi dài để học đồng thời chi tiết cục bộ và cấu trúc toàn ảnh. |
| Le et al. (2026). [CG-GLORE](https://arxiv.org/abs/2608.15246), preprint | Dùng conjugate gradient cho bước cập nhật có mô hình phép chiếu và mạng học đặc trưng cục bộ lẫn toàn cục. |

Hai bài đánh giá sparse-view CT. Nhóm kế thừa ý tưởng phương pháp và xây dựng thử nghiệm riêng cho các cung góc liên tục của limited-angle CT.

## Nghiên cứu limited-angle CT

| Hướng | Bài đại diện |
| --- | --- |
| Tối ưu lặp và ràng buộc có hướng | [Directional-TV](https://pmc.ncbi.nlm.nih.gov/articles/PMC8044061/) · [Frikel & Quinto](https://doi.org/10.1088/0266-5611/29/12/125007) |
| Kết hợp mạng học với phép chiếu | [Unrolled SART + U-Net](https://pubmed.ncbi.nlm.nih.gov/36541524/) · [Learning the Invisible](https://doi.org/10.1088/1361-6420/ab10ca) |
| Hoàn thiện sinogram | [Sinogram Completion, ICIP 2025](https://arxiv.org/abs/2505.19385) · [PCGA-Net, 2026](https://pmc.ncbi.nlm.nih.gov/articles/PMC13729243/) |
| Diffusion có ràng buộc số đo | [DOLCE, ICCV 2023](https://openaccess.thecvf.com/content/ICCV2023/papers/Liu_DOLCE_A_Model-Based_Probabilistic_Diffusion_Framework_for_Limited-Angle_CT_Reconstruction_ICCV_2023_paper.pdf) · [Geometry-Aware Diffusion, 2026, preprint](https://arxiv.org/abs/2610.08866) |
| Tối ưu biểu diễn ảnh riêng từng ca | [Iterative Reconstruction with INR](https://pubmed.ncbi.nlm.nih.gov/38593820/) · [Prior-Guided Residual INR, 2026](https://pubmed.ncbi.nlm.nih.gov/43042532/) |
| Benchmark và dữ liệu | [DM4CT, ICLR 2026](https://arxiv.org/abs/2602.18589) · [LoDoPaB-CT](https://pmc.ncbi.nlm.nih.gov/articles/PMC8052416/) |

[Quay lại kế hoạch nghiên cứu](../docs/PLAN.md)
