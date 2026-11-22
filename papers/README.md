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

## Methods from Related Imaging Problems

These papers offer ideas for the baseline, the reconstruction method, and the training setup. Each idea would be evaluated under our own limited-angle CT protocol.

| Paper | Original problem and method | How it could inform this project |
| --- | --- | --- |
| Jin et al. (2017), [Deep Convolutional Neural Network for Inverse Problems in Imaging (FBPConvNet)](https://arxiv.org/abs/1611.03679) | Sparse-view CT. A multiscale residual CNN refines an FBP reconstruction. | Use FBP followed by a CNN as a learned baseline, then measure what scan-arc conditioning and projection-based refinement add. |
| Adler & Öktem (2018), [Learned Primal-Dual Reconstruction](https://arxiv.org/abs/1707.06474) | Low-dose CT. An unrolled primal-dual network updates image and measurement representations using the forward model. | Consider an iterative design that exchanges information between the image and sinogram throughout reconstruction. |
| Aggarwal et al. (2019), [MoDL](https://pmc.ncbi.nlm.nih.gov/articles/PMC6760673/) | Undersampled MRI. A shared CNN prior alternates with a conjugate-gradient data-consistency step. | Adapt the alternating updates using the limited-angle CT projection operator in place of the MRI encoding operator. |
| Hendriksen et al. (2020), [Noise2Inverse](https://arxiv.org/abs/2001.11801) | Tomographic denoising. A self-supervised CNN uses separate reconstructions from disjoint subsets of noisy measurements. | Explore projection splitting for an experiment on measurement noise when clean references are scarce. The available scan arc still determines which edges are observable. |

[Back to the research plan](../docs/PLAN.md)
