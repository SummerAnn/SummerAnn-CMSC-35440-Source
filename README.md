# CMSC 35440 Machine Learning in Biology and Medicine
## Homework 2: Cancer Site Classification from Histopathology Features
**Released**: Jan 26,2026

**Due**: Feb 2,2026 at 11:59 PM Chicago Time on Gradescope

**In this homework, you'll explore embeddings of histopathology image features for three different cancer types.**

This assignment is inspired by the [Cancer Site Classification](https://github.com/zhangrenyuuchicago/CancerSiteClassification) project by Renyu Zhang, which demonstrates how deep learning can be used to classify cancer types from histopathology whole slide images (WSI). The original project uses Inception-V3 to extract features from image tiles and trains a classifier to distinguish between colorectal adenocarcinoma (COAD) and uterine corpus endometrial carcinoma (UCEC). However, that approach requires GPUs, downloading large slide files, and significant computational resources.

In this homework, we adapt the same core concept—cancer site classification from histopathology—but make it accessible for homework by using **pre-extracted features** from a modern vision transformer (UNI2-h). This allows us to focus on the downstream analysis: understanding how different cancer types cluster in feature space, visualizing embeddings, and analyzing model behavior—all without requiring GPUs.

We'll work with three distinct cancer types:
- **Diffuse large B-cell lymphoma (DLBC)**: The most common type of non-Hodgkin lymphoma, originating from B-cells in the lymphatic system.
- **Cholangiocarcinoma (CHOL)**: A rare but aggressive cancer that originates in the bile ducts, which carry bile from the liver to the small intestine.
- **Uveal melanoma (UVM)**: A rare cancer that develops in the uvea (the middle layer of the eye), which includes the iris, ciliary body, and choroid.

These three cancers affect very different organ systems (lymphatic, digestive, and ocular), making them an interesting test case for whether histopathology features can capture organ-specific morphological patterns. Histopathology slides from all three can present diagnostic challenges, especially in cases with unusual morphological features or when tissue samples are limited.

In this homework, you'll work with a third party embedding model for whole slide images (WSI) using UNI2-h, a state-of-the-art vision transformer model trained on histopathology images. UNI2-h was trained using self-supervised learning on a large collection of histopathology images and can extract meaningful representations from tissue slides. You may want to think of these as pre-extracted features.  The embeddings we will use are pre-computed embeddings from the MahmoodLab/UNI2-h-features dataset on Hugging Face.
By using precomputed embeddings, we avoid the need for GPUs and can focus on the downstream analysis: clustering, visualization, and understanding model behavior. This mirrors real-world scenarios where embeddings might be done once and reused for multiple analyses.
Last, you'll practice a vital step for biomedical machine learning: expert review. Before these models can ever be deployed in real patient settings, the- must undergo rigorous review. In the US, any medical products intended for patient usage must be approved by the FDA. An excellent historical case of demonstrating why we need such review is Thalidomide in the late 1950s. It was originally marketed in Europe as a treatment for morning sickness, especially during pregnancy. However, the drug was blocked in the US by an expert reviewer at the FDA, Dr. Frances Kelsey (a UChicago MD/PhD alum!), who was concerned over the lack of evidence concerning the drug's safety. She was of course right to be concerned, as Thalidomide was shown to cause severe birth defects, leading to its removal from European markets. Suffice to say, expert review is crucial to patient safety, especially as we dive into this new age of AI/ML in medicine.
