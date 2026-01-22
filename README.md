CMSC 35440 Machine Learning in Biology and Medicine
Homework 1: Embedding Immunology Research Articles
Released: Jan 12, 2026

Due: Jan 23, 2026 at 11:59 PM Chicago Time on Gradescope

In this first homework, you'll generate embeddings for 28 immunology research articles and visualize them using various dimensionality reduction techniques.

At a high-level, embeddings are vectors computed by some algorithm or model that "code" information from data. For this homework, you will code text documents as vectors using the bag of words algorithm and normalize these vectors using the term-frequency inverse document frequency (TF-IDF) method. TF-IDF downweights ubiquitous terms and highlights vocabulary that is distinctive to each paper (e.g., checkpoint, cGAS-STING, germinal center). This helps the embeddings reflect biological themes rather than common filler, so downstream plots can separate immune subfields and detect cross-cutting topics.

The 28 papers span three major areas of immunology:

T-cell biology: CD8+ T cell exhaustion, checkpoint inhibition, cancer immunotherapy
B-cell biology: Germinal centers, antibody responses, T follicular helper cells
Innate immunity: TLRs, cGAS-STING pathway, macrophages, autophagy
All papers are from journals like Immunity, Cell, Nature Reviews, and Annual Reviews (2015-2024).

For this homework, you will code text documents as vectors using the bag of words algorithm and normalize these vectors using the term-frequency inverse documentation frequency (TF-IDF) method. This method dates back over 50 years to 1972. Through this homework, hopefully we'll convince you that it's still very much relevant.
