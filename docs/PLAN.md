# Research Plan

**Status:** Literature review and proposal preparation. The milestones below are open for team discussion.

## Problem and Hypothesis

In the sparse-view CT setups studied by the two papers provided by the instructor, a small number of measurement angles are distributed across the full angular range. In limited-angle CT, measurements are confined to a continuous arc, such as 90° out of the 180° range for 2D parallel-beam CT. Rotating the scan arc changes which edge orientations are difficult to recover.

**Research question:** With the architecture and training data held fixed, does giving the U-Net the position and width of the scan arc improve edge preservation across orientations when the model encounters an unseen arc?

## Proposed Method

1. Use **filtered back projection (FBP)** to reconstruct an initial image from the measured angles.
2. Use a **small U-Net** to predict a correction to the initial image. Give the network the position and width of the scan arc.
3. Forward-project the predicted image at the measured angles and use the difference from the input sinogram to refine the image (*data consistency*).

The long-sequence modeling paper motivates learning fine local detail alongside long-range structure. CG-GLORE motivates using the projection model to update the reconstruction. [Papers provided by the instructor and related work](../papers/README.md#papers-provided-by-the-instructor)

## Experimental Design

| Item | Proposed setup |
| --- | --- |
| Data | Start with phantoms containing small structures at different orientations. Then evaluate on a subset of [LoDoPaB-CT](https://pmc.ncbi.nlm.nih.gov/articles/PMC8052416/) with simulated sinograms. Split the CT data by patient. |
| Scan arcs | Train with 60° and 120° arcs at several positions. Test unseen arc positions and an unseen 90° arc width separately. Keep the number of projections fixed when comparing arc positions at the same width. |
| Baselines | FBP and iterative reconstruction with total variation (TV). |
| Ablation study | Keep the U-Net architecture and data splits fixed. Compare four configurations by enabling or disabling scan-arc conditioning and projection-based refinement independently. |
| Metrics | PSNR, SSIM, reprojection error at the measured angles, and edge F1 scores by orientation group on the phantoms. |
| Visual evaluation | Compare reconstructions as the scan arc rotates. Zoom in on small structures and mark missing or spurious edges on the phantoms. |

Reconstructions with similar agreement at the measured angles can still differ at edges that are difficult to observe. We will interpret projection errors alongside the edge metrics and reference images. [Learning the Invisible](https://doi.org/10.1088/1361-6420/ab10ca)

## Progress

- [x] Review the two papers provided by the instructor and related limited-angle CT research.
- [ ] Finalize the research question and experimental setup in the proposal.
- [ ] Generate limited-angle sinograms and run the FBP and TV baselines.
- [ ] Train the U-Net variants and test them on unseen scan arcs.
- [ ] Summarize the metrics and analyze reconstruction failures.
- [ ] Complete the report and demo.

## Decision Log

| Status | Decision | Rationale |
| --- | --- | --- |
| Proposed | Start with 2D parallel-beam geometry. | Control arc position, arc width, and projection count in each comparison. |
| Proposed | Use a small U-Net as the main model. | Keep training costs low enough to evaluate all four configurations. |
| Proposed | Test unseen arc positions and unseen arc widths separately. | Measure generalization to position and width independently. |
