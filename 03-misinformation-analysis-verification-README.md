# Misinformation Analysis & Verification

A prototype exploring misinformation analysis through NLP-based semantic similarity, image-analysis experiments, and hash-based claim integrity logging.

> **Status:** Existing Academic Prototype  
> This repository documents the implementation that was developed as part of the original academic misinformation project. It should not be interpreted as a production-grade automated fact-checking system.

## Overview

The original project explored the broader idea of combining AI-based misinformation analysis with integrity and verification mechanisms.

The implementation contains several experimental components:

- semantic similarity analysis of news claims
- Sentence Transformer embeddings
- comparison against manually curated trusted statements
- hash-based claim records
- exploratory image classification
- a placeholder deepfake-detection component

## NLP / Semantic Similarity Component

The current NLP prototype uses:

`all-MiniLM-L6-v2`

to generate sentence embeddings.

The embeddings are compared using cosine similarity.

```text
Input Claim
     |
     v
Sentence Transformer
     |
     v
Semantic Embedding
     |
     v
Cosine Similarity
     |
     v
Comparison with Curated Trusted Statements
     |
     v
Similarity / Bias-Related Heuristic
```

The trusted reference set is manually curated.

The current implementation therefore demonstrates semantic comparison rather than independently establishing whether a claim is factually true.

## Hash-Based Verification Component

The prototype maintains block-like records containing fields such as:

- index
- timestamp
- content hash
- original claim
- verdict
- confidence
- bias delta
- verification status

SHA-256 is used to generate a hash from the claim.

This is a **blockchain-inspired integrity mechanism**, not a production blockchain network.

## Image Analysis Component

An exploratory Xception-based image classification component was developed for binary image classification:

- Fake
- Real

The current implementation is experimental and requires further validation before reliable fake-image detection can be claimed.

A deepfake-detection function is also present as a placeholder and does not constitute a functioning deepfake detector.

## Current Limitations

The current prototype does not provide:

- a properly trained general-purpose misinformation classifier
- a validated fact-checking dataset
- reliable external evidence retrieval
- a production blockchain network
- a validated deepfake detector
- comprehensive model evaluation
- a production-ready real/fake image classifier

These limitations are documented deliberately so that the repository accurately reflects the implementation.

## Planned Cleanup

Future development may include:

- refactoring duplicated code
- correcting implementation issues
- separating NLP, image, and verification modules
- adding unit tests
- improving data handling
- adding proper evaluation
- improving reproducibility
- separating experimental components from implemented functionality

Any extension will remain deliberately lightweight and understandable.

## Planned Repository Structure

```text
misinformation-analysis-verification/
├── src/
│   ├── nlp/
│   ├── image/
│   └── verification/
├── data/
├── notebooks/
├── tests/
├── requirements.txt
├── README.md
└── .gitignore
```

## Technology Stack

- Python
- Sentence Transformers
- PyTorch
- scikit-learn
- NumPy
- Pandas
- Matplotlib
- OpenCV / PIL where applicable
- SHA-256 hashing

## Learning Outcomes

- Sentence embeddings
- Semantic similarity
- NLP experimentation
- Image classification concepts
- Hashing
- Verification data structures
- Model limitations
- Responsible interpretation of ML outputs
