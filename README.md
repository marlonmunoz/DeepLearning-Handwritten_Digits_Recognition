# DeepLearning:
## Handwritten Digits Recognition

## Project Overview
This project demonstrates handwritten digit recognition using the MNIST dataset, comparing two approaches: a traditional neural network and a Convolutional Neural Network (CNN).

## Walkthrough

### Without CNN (Traditional Neural Network)

1. **Data Preprocessing**
   - Load MNIST dataset (28x28 pixel images)
   - Flatten images into 1D vectors (784 features)
   - Normalize pixel values (0-255) to range (0-1)
   - One-hot encode labels (0-9)

2. **Model Architecture**
   - Input layer: 784 neurons (flattened image)
   - Hidden layers: Fully connected dense layers
   - Output layer: 10 neurons (one per digit)
   - Activation: ReLU for hidden, Softmax for output

3. **Training**
   - Loss function: Categorical cross-entropy
   - Optimizer: Adam or SGD
   - Train on full dataset with backpropagation

4. **Limitations**
   - Loses spatial information by flattening
   - More parameters to train
   - Lower accuracy (~97-98%)
   - No translation invariance

### With CNN (Convolutional Neural Network)

1. **Data Preprocessing**
   - Load MNIST dataset (28x28 pixel images)
   - Reshape to (28, 28, 1) to preserve spatial structure
   - Normalize pixel values to (0-1)
   - One-hot encode labels

2. **Model Architecture**
   - **Convolutional layers**: Extract features (edges, curves)
   - **Pooling layers**: Reduce dimensionality, retain important features
   - **Flatten layer**: Convert 2D features to 1D
   - **Dense layers**: Classification
   - Output: 10 neurons with Softmax

3. **Training**
   - Loss function: Categorical cross-entropy
   - Optimizer: Adam
   - Learns spatial hierarchies automatically

4. **Advantages**
   - Preserves spatial relationships
   - Translation and rotation invariance
   - Fewer parameters due to weight sharing
   - Higher accuracy (~99%+)
   - Better generalization

## Key Differences

| Aspect | Without CNN | With CNN |
|--------|-------------|----------|
| Input shape | Flattened (784,) | 2D image (28,28,1) |
| Spatial info | Lost | Preserved |
| Parameters | More | Fewer |
| Accuracy | ~97-98% | ~99%+ |
| Feature learning | Manual/none | Automatic |