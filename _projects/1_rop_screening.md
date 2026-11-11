---
layout: page
title: Interpretable ROP screening
description: Clinically guided ensemble for retinopathy of prematurity staging and Plus Disease detection
img: assets/img/projects/rop_attention.jpg
importance: 1
category: research
---

Retinopathy of prematurity (ROP) is a leading cause of preventable childhood blindness, and screening it automatically is hard for two reasons. Public datasets are small and highly imbalanced, and the diagnosis depends on two different kinds of evidence: large structural changes such as the fibrovascular ridge, and fine changes in the blood vessels (Plus Disease). Most existing models either need very large private datasets or simply concatenate clinical data with image features at the last layer.

I designed the Context-Aware Asymmetric Ensemble, which splits the problem the way a clinician would. A structure stream (MS-AQNet) uses gestational age, birth weight and post-conceptual age as a query that guides where the network looks in the fundus image, with a learnable gate so the model falls back on the image when clinical inputs are missing or inconsistent. A texture stream (VascuMIL) analyzes high-resolution patches together with vessel topology maps using gated multiple instance learning. A small meta-learner then combines the two.

On a public cohort of 188 infants (6,004 images), the ensemble reached a macro F1-score of 0.93 for broad ROP staging and an AUC of 0.996 for Plus Disease detection, with attention heatmaps and vascular threat maps that show what each stream relied on. External validation on other populations is still needed.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/rop_pipeline.jpg" title="CAA Ensemble pipeline" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Overview of the framework: artifact removal, vessel topology extraction, and fusion of the structure and texture streams.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/rop_attention.jpg" title="Attention and vascular threat maps" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Structure-stream attention (middle) and texture-stream vascular threat maps (right) for example fundus images.
</div>

**Publication:** Md. Mehedi Hassan and Taufiq Hasan, _Computers in Biology and Medicine_ (2026).
[Paper](https://doi.org/10.1016/j.compbiomed.2026.111945) · [arXiv](https://arxiv.org/abs/2602.05208) · [Code](https://github.com/mubid-01/CAA_Ensemble)
