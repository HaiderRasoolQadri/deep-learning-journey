# Feedforward Propagation in Neural Networks
---
**Feedforward propagation** is the process of moving input data through a neural network layer by layer to compute the output. No learning happens here; it’s purely **forward calculation**.

## 1. Structure of a Neural Network
- **Input layer** – Receives input features.  
- **Hidden layers** – Process information using weights, biases, and activation functions.  
- **Output layer** – Produces the final prediction.

## 2. Mathematical Steps

1. **Input Layer:**  
   Let input features be:  
   $$
   X = [x_1, x_2, \dots, x_n]
   $$

2. **Weighted Sum at Neurons:**  
   $$
   z = W \cdot X + b
   $$
   Where:  
   - $W$ = weights  
   - $b$ = bias  
   - $X$ = input features

3. **Activation Function:**  
   $$
   a = f(z)
   $$
   Common activations:  
   - Sigmoid: $\sigma(z) = \frac{1}{1 + e^{-z}}$  
   - ReLU: $\text{ReLU}(z) = \max(0, z)$  
   - Tanh: $\tanh(z)$

4. **Pass to Next Layer:**  
   Output $a$ becomes input for the next layer, repeat steps 2–3.

5. **Output Layer:**  
   - Regression → linear activation  
   - Classification → sigmoid (binary) or softmax (multi-class)  
   $$
   \hat{y} = f_\text{output}(W_\text{out} \cdot a_\text{last} + b_\text{out})
   $$