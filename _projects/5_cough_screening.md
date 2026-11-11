---
layout: page
title: Offline cough-based respiratory screening
description: Edge-AI app for pneumonia, pertussis and bronchitis screening from cough sounds
img: assets/img/projects/cough_spectrograms.jpg
importance: 5
category: research
---

Respiratory infections cause far more deaths in low- and middle-income countries, where laboratory tests and chest imaging are often unavailable. Cough sounds are a low-cost screening signal, but many published models rely on cloud computing, are not robust to background noise, or are evaluated in ways that leak recordings from the same patient between training and testing.

With three co-authors, I built a screening pipeline that isolates cough events using dual-threshold hysteresis gating, converts them to log-Mel spectrograms, and classifies them with an EfficientNet-B1 network. We compiled recordings from 426 subjects across public datasets and used nested, subject-aware cross-validation so that no patient appeared in both training and test sets.

The model achieved 85% patient-level accuracy, with AUCs of 1.00 for healthy controls, 0.99 for pertussis, 0.94 for bronchitis and 0.92 for pneumonia. Bronchitis and pneumonia were the classes most often confused with each other. The full pipeline runs offline in an Android app (Flutter with Chaquopy), taking about 2–4 seconds on a mid-range phone.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/cough_pipeline.jpg" title="Signal processing pipeline" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Preprocessing and cough event detection, from raw audio to log-Mel spectrogram.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/cough_attribution.jpg" title="Integrated Gradients attribution" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Integrated Gradients attribution maps showing which time–frequency regions drove the predictions.
</div>

**Publication:** Accepted at the 2nd International Conference on Advances in Computing, Communication, Electrical, and Smart Systems (IEEE), 2026.
