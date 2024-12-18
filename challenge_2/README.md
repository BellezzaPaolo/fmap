# Mars Terrain Segmentation Challenge 🚀🔴

## Project Overview
Embark on an interplanetary machine learning journey! This project tackles the challenge of accurately segmenting Martian surface images into distinct terrain classes, pushing the boundaries of deep learning in planetary exploration.

## Dataset Exploration 🛰️
- **Total Images**: 2,615 training | 10,022 testing
- **Image Specifications**: 
  - Grayscale
  - Dimensions: 64x128 pixels
- **Terrain Classes**: 
  1. Background
  2. Soil
  3. Bedrock
  4. Sand
  5. Large Rocks

### Initial Challenges
- 110 outlier images with irrelevant content
- Extreme class imbalance, particularly for large rocks class

## Preprocessing Strategies 🛠️
### Data Augmentation Approaches
1. **Version 1**: Standard Augmentation
   - Random flipping
   - Cropping
   - Rotation
   - Translation
   - Expanded dataset to 4,000 images

2. **Version 2**: Targeted Large Rocks Enhancement
   - Focused augmentation on rare large rocks class
   - Increased large rocks class images to 900

3. **Version 3**: Synthetic Image Generation
   - Pasting large rocks onto images lacking them
   - Further dataset expansion

### Augmentation Exploration
- Experimented with color-based augmentations
- Ultimately abandoned due to performance degradation

## Model Architecture Evolution 🧠
### Base Model: U-Net
- Standard segmentation architecture
- Modifications:
  - SeparableConvolutions to reduce parameters
  - Group Normalization
  - ReLU activation

### Advanced Architecture Explorations
1. **U-Net++ Approach**
   - Nested architecture with intermediate upsampling blocks
   - Skip connections for multi-level feature extraction

2. **Concatenated Model Configurations**
   - Simultaneous training of two models
   - Complex model output as input for simpler model
   - Tested configurations:
     - Two U-Nets
     - Two U-Net++ models

## Innovative Techniques 💡
### Bottleneck Improvements
- Dilated Convolutions
- Global Context Modules
- Squeeze-and-Excitation Blocks

### Loss Function Engineering
Explored sophisticated loss function combinations:
- Dice Loss
- Focal Loss
- Boundary Loss
- Sparse Categorical Cross-Entropy

**Final Approach**: Primarily sparse categorical cross-entropy

## Performance Metrics 📊
### Model Comparison
| Model | Validation Mean IoU | Test Mean IoU |
|-------|---------------------|---------------|
| U-Net | 0.3810 | 0.4442 |
| U-Net++ | 0.4765 | 0.4932 |
| Concatenated U-Net | 0.6405 | 0.6324 

## Top Performer
**Concatenated U-Net**
- Simplest training process
- Reduced number of parameters
- Most consistent performance

## Computational Challenges 💻
- Performance metric peaks mid-training
- Balancing model complexity with efficiency
- Managing training time and early stopping
- Optimizing computational resources

## Technologies Used
![Python](https://img.shields.io/badge/Python-3.x-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![Keras](https://img.shields.io/badge/Keras-2.x-red)

## Repository Contents
- `fmap.ipynb`: Final model implementation
- Supporting notebooks
- Comprehensive project report

## Team Contributions 👥
- **Filippo Galli**: 
  - Loss function implementation
  - U-Net++ implementation
  - Neural network experiments

- **Alessandro Howe**: 
  - U-Net++ implementation
  - Concatenated U-Net++ development
  - Neural network experiments

- **Matteo Callini**: 
  - Concatenated U-Net++ and U-Net implementation
  - Ensemble loss parameter experiments

- **Paolo Bellezza**: 
  - Data exploration and augmentation
  - U-Net implementation
  - Ensemble loss parameter experiments

## References
1. Liu et al., "A Hybrid Attention Semantic Segmentation Network for Unstructured Terrain on Mars", 2023
2. Zhou et al., "UNet++: A Nested U-Net Architecture for Medical Image Segmentation", 2018

## Potential Future Improvements
- Optimize ensemble loss hyperparameters
- Improve metric monotonicity during training
- Explore alternative losses for intermediate outputs
- Implement more advanced attention mechanisms