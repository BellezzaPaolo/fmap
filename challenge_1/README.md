# Blood Cell Classification Challenge 🔬🧬

## Project Overview
In this advanced machine learning project, we developed a sophisticated deep learning model to classify blood cell images into eight distinct cell types. The challenge demanded not just high accuracy, but robust preprocessing and generalization techniques.

## Dataset Characteristics
- **Total Images**: 13,759
- **Number of Classes**: 8
- **Initial Challenges**:
  - 1,800 outlier images with irrelevant backgrounds
  - Significant class imbalance (from 1,049 to 2,530 images per class)

## Preprocessing Strategies 🛠️
### Data Cleaning
- Removed outlier images with non-medical backgrounds
- Rejected initial background removal techniques to preserve image information

### Data Augmentation
We implemented a sophisticated multi-stage augmentation approach:
1. **Version 1**: Initial augmentation techniques
2. **Version 2**: Light transformations (contrast, brightness, flipping)
3. **Version 3**: Advanced augmentation using RandAugment and AugMix
4. **Final Version**: Hybrid approach combining basic and custom transformations

**Result**: Balanced dataset with 3,000 images per class

## Model Development 🧠
### Approach Evolution
1. **Initial Phase**: Custom architectures inspired by AlexNet
2. **Transfer Learning**: Leveraging pre-trained models from ImageNet
   - Explored: VGG16, MobileNetV3, ResNet, Xception, EfficientNetV2S, NASNetMobile

### Model Optimization Techniques
- Dropout layer (0.3 rate)
- L2 regularization
- Early stopping
- Normalization techniques
- AdamW optimizer

## Final Models 🏆
### Top Performing Models
1. **EfficientNetV2s**
   - Local Test Accuracy: 0.9875
   - CodaBench Accuracy: 0.85
   - Key Strengths: High accuracy, resource efficiency

2. **NASNetMobile**
   - Local Test Accuracy: 0.8757
   - CodaBench Accuracy: 0.77

3. **Xception**
   - Local Test Accuracy: 0.9791
   - CodaBench Accuracy: 0.68

## Computational Challenges 💻
- Limited RAM constraints
- Session crashes during large-scale augmentation
- Optimizing computational time
- Handling training complexities with multi-GPU setups

## Key Insights 💡
- Transfer learning proves more effective than custom architectures
- Careful augmentation is crucial for model generalization
- Balancing model complexity with computational efficiency

## Technologies Used
![Python](https://img.shields.io/badge/Python-3.x-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![Keras](https://img.shields.io/badge/Keras-2.x-red)

## Repository Contents
- `fmap.ipynb`: Final model implementation
- Supporting notebooks
- Detailed project report

## Team 👥
- **Filippo Galli**: NASNetMobile experiments, code optimization
- **Alessandro Howe**: Xception model, overfitting prevention
- **Matteo Callini**: EfficientNetV2 model, early custom model exploration
- **Paolo Bellezza**: Data exploration, augmentation techniques

## References
1. Ashgar et al., "Automatic classification of blood cells using transfer learning", Informatics in Medicine Unlocked, 2024

## Potential Future Work
- Explore more advanced augmentation techniques
- Investigate ensemble methods
- Fine-tune with more trainable parameters
- Experiment with newer model architectures