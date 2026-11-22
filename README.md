# Limited-Angle CT Reconstruction

Course project for **SE374: Development of Medical Image Processing Software**. The team is reviewing the literature and preparing a research proposal.

## Goal

Reconstruct 2D CT images from projections acquired over a limited angular range. We will test whether giving a small U-Net information about the scan arc helps preserve edges of different orientations when the model encounters an unseen scan arc. We will refine the output using the measured projections and compare the results with filtered back projection (FBP) and iterative reconstruction with total variation (TV).

## Repository Layout

- [`docs/PLAN.md`](docs/PLAN.md) — Research question, proposed method, experimental design, and progress checklist.
- [`papers/README.md`](papers/README.md) — The two papers provided by the instructor and related work organized by research direction.
