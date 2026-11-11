---
layout: page
title: Error-resilient fetal ultrasound dating
description: Undergraduate thesis with Johns Hopkins University and the Projahnmo Research Foundation
importance: 2
category: research
---

In many low-resource settings, women first attend antenatal care late in pregnancy, and ultrasound scans are often performed and recorded by health workers with limited specialist training. Gestational age estimates at this stage are less reliable, measurements are sometimes mistyped or missing, and deep learning models can learn shortcuts from on-screen text and calipers instead of fetal anatomy.

For my undergraduate thesis, I developed the HeadsUp Attention Network for late-gestation fetal dating and adverse pregnancy outcome prediction (small for gestational age, preterm birth and low birth weight), using data from the WHO AMANHI and Projahnmo Research Foundation cohorts. The model combines the fetal head ultrasound image with head biometrics through a discrepancy-gating module that suppresses mistyped and missing clinical measurements. Weakly supervised localization keeps the model focused on the fetal head and removes "Clever Hans" shortcuts from the ultrasound interface.

The model estimates gestational age with a mean absolute error of 3.6–3.7 days, and an offline tool based on it is in early clinical testing. The manuscript is under internal review before submission.

**Supervisor:** Dr. Taufiq Hasan, BUET · **Principal investigator:** Dr. Abdullah Baqui, Department of International Health, Johns Hopkins University
