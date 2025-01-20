# PyTorch

## Overview

PyTorch is an open-source machine learning library developed by Facebook's AI Research lab. It is widely used for deep learning applications such as natural language processing and computer vision. PyTorch provides a flexible and intuitive interface for building and training neural networks.

## Installation and Setup

1. **Install Python**: Ensure you have Python installed. You can download it from the [official Python website](https://www.python.org/downloads/).
2. **Install PyTorch**: Open a terminal and run the following command to install PyTorch:
   ```sh
   pip install torch torchvision
   ```

## Simple Example Using PyTorch

Here is a simple example of creating and training a neural network using PyTorch:

```python
import torch
import torch.nn as nn
import torch.optim as optim

# Define a simple neural network
class SimpleNN(nn.Module):
    def __init__(self):
        super(SimpleNN, self).__init__()
        self.fc1 = nn.Linear(10, 5)
        self.fc2 = nn.Linear(5, 1)

    def forward(self, x):
        x = torch.relu(self.fc1(x))
        x = self.fc2(x)
        return x

# Create a random input tensor
input_tensor = torch.randn(10)

# Create the neural network
model = SimpleNN()

# Define a loss function and optimizer
criterion = nn.MSELoss()
optimizer = optim.SGD(model.parameters(), lr=0.01)

# Forward pass
output = model(input_tensor)
target = torch.randn(1)
loss = criterion(output, target)

# Backward pass and optimization
optimizer.zero_grad()
loss.backward()
optimizer.step()

print("Training complete")
```

## Key Features and Common Use Cases

- **Dynamic Computation Graphs**: PyTorch uses dynamic computation graphs, which allow for more flexibility and easier debugging.
- **GPU Acceleration**: PyTorch supports GPU acceleration, making it suitable for training large-scale neural networks.
- **Extensive Library**: PyTorch provides a wide range of pre-built neural network layers, loss functions, and optimization algorithms.
- **Community and Ecosystem**: PyTorch has a large and active community, with many pre-trained models and libraries available for various tasks.

## Official Documentation

For more information, visit the [official PyTorch documentation](https://pytorch.org/docs/).
