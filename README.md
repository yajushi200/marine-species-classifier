# 🐠 Marine Species Classifier

**Comparing three deep learning approaches for classifying marine animals with limited data.**
Best result: **91.82% accuracy** with ResNet50 transfer learning.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Deep Learning](https://img.shields.io/badge/Deep%20Learning-CNN-blue?style=flat-square)
![Transfer Learning](https://img.shields.io/badge/Transfer%20Learning-ResNet50-success?style=flat-square)

---

## The problem

Monitoring marine biodiversity needs accurate automated species classification, but it is hard:
- labelled underwater datasets are small
- many species look very similar
- underwater photos have poor lighting, murky water and cluttered backgrounds

## The approach

A curated, balanced dataset of **5,978 images across 10 classes** (from an original 23-class set), split 70 / 15 / 15 for train, validation and test. Three paradigms were compared:

1. **Custom CNNs trained from scratch**: baseline, medium and VGG-style architectures
2. **Unsupervised pre-training** with autoencoders, then classification
3. **Transfer learning** from ImageNet with ResNet50 and EfficientNet-B0, using two-phase training (frozen backbone, then full fine-tuning) and data augmentation

## Results

| Approach | Best model | Accuracy |
|---|---|---|
| Transfer learning | **ResNet50** | **91.82%** |
| Transfer learning | EfficientNet-B0 | 90.13% |
| Custom CNN | Medium CNN | 50.11% |
| Autoencoder pre-training | | 8 to 11% below supervised |

**Key findings**
- Transfer learning beat training from scratch by **27 to 41 percentage points**
- Autoencoder pre-training hurt performance, because image reconstruction does not line up with classification
- Remaining errors were between biologically similar species, like dolphins vs whales and sea rays vs sharks

## Documentation

📄 [Full research paper](https://github.com/yajushi200/MyPortfolio/blob/main/MarineSpecies.pdf): methodology, training setup, confusion analysis and discussion.

## Team

Arshdeep Kaur, Varun Rohit Mudunuri, Jaekyeong Jang, Younghun Mun, Miguel Chadid Rendon and **Yajushi Garg**, Centennial College.

## Code

Code from the team's earlier experiments (23-class version) is in [varunrohit12/Marine-Species-Classification](https://github.com/varunrohit12/Marine-Species-Classification). The results above are from the final 10-class study in the paper.
