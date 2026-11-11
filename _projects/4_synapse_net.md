---
layout: page
title: SYNAPSE-Net
description: One framework for segmenting white matter hyperintensities, stroke lesions and brain tumors
img: assets/img/projects/synapse_qualitative.jpg
importance: 4
category: research
---

Brain lesion segmentation models are usually built for one pathology at a time, and their performance can vary widely from case to case, especially for small or irregular lesions. SYNAPSE-Net is a single hybrid CNN–Transformer architecture designed to segment clinically different lesions while reducing that variance.

Each MRI sequence is processed by its own convolutional encoder. In the bottleneck, Swin Transformer layers add global context and a cross-modal attention fusion module combines the sequences. A hierarchical gated decoder, built on UNet++, then uses deep features to refine the skip connections. Training uses difficulty-aware sampling for small lesions and loss functions adapted to each pathology.

We evaluated the framework on three public challenges. On the WMH MICCAI 2017 test set, which includes scanners absent from training, it achieved a Dice score of 0.831 and an HD95 of 3.03. It also achieved an HD95 of 9.69 on ISLES 2022 (internal validation split) and a tumor core Dice score of 0.8651 on BraTS 2020.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/synapse_architecture.jpg" title="SYNAPSE-Net architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Architecture: parallel CNN encoders, a hybrid Swin Transformer and cross-modal attention bottleneck, and a hierarchical gated decoder.
</div>
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/synapse_qualitative.jpg" title="WMH segmentation examples" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Example WMH segmentations from the architecture ablation: true positives (green), false negatives (red) and false positives (blue).
</div>

**Preprint:** Md. Mehedi Hassan, Shafqat Alam, Shahriar Ahmed Seam and Maruf Ahmed (under review).
[arXiv](https://arxiv.org/abs/2510.26961) · [Code](https://github.com/mubid-01/SYNAPSE-Net-pre)
