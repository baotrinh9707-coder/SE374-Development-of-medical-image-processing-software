# References

## Papers Provided by the Instructor

| Paper | Relevance to this project |
| --- | --- |
| Bui, Le & Nguyen (2026). [Long-sequence modeling for sparse-view computed tomography reconstruction](https://link.springer.com/article/10.1007/s00138-026-01901-1) | Uses 2×2 tokens and long-sequence models to capture fine local detail and structure across the image. |
| Le et al. (2026). [CG-GLORE](https://arxiv.org/abs/2608.15246), preprint | Uses conjugate gradient for updates that incorporate the projection model and a network that learns local and global features. |

Both papers evaluate sparse-view CT. Their methods inform our approach, which we will test separately on limited-angle CT with continuous scan arcs.

## Related Work on Limited-Angle CT

| Research direction | Representative papers |
| --- | --- |
| Iterative optimization with directional constraints | [Directional-TV](https://pmc.ncbi.nlm.nih.gov/articles/PMC8044061/) · [Frikel & Quinto](https://doi.org/10.1088/0266-5611/29/12/125007) |
| Learned reconstruction with a projection model | [Unrolled SART + U-Net](https://pubmed.ncbi.nlm.nih.gov/36541524/) · [Learning the Invisible](https://doi.org/10.1088/1361-6420/ab10ca) |
| Sinogram completion | [Sinogram Completion, ICIP 2025](https://arxiv.org/abs/2505.19385) · [PCGA-Net, 2026](https://pmc.ncbi.nlm.nih.gov/articles/PMC13729243/) |
| Diffusion with measurement consistency | [DOLCE, ICCV 2023](https://openaccess.thecvf.com/content/ICCV2023/papers/Liu_DOLCE_A_Model-Based_Probabilistic_Diffusion_Framework_for_Limited-Angle_CT_Reconstruction_ICCV_2023_paper.pdf) · [Geometry-Aware Diffusion, 2026, preprint](https://arxiv.org/abs/2610.08866) |
| Per-scan optimization with implicit neural representations | [Iterative Reconstruction with INR](https://pubmed.ncbi.nlm.nih.gov/38593820/) · [Prior-Guided Residual INR, 2026](https://pubmed.ncbi.nlm.nih.gov/43042532/) |
| Benchmarks and datasets | [DM4CT, ICLR 2026](https://arxiv.org/abs/2602.18589) · [LoDoPaB-CT](https://pmc.ncbi.nlm.nih.gov/articles/PMC8052416/) |

[Back to the research plan](../docs/PLAN.md)
