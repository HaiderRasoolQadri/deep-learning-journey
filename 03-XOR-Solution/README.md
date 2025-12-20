# XOR Problem and Perceptron Limitation

## 1. XOR Function

The XOR (exclusive OR) function is defined as:

\[
\text{XOR}(x_1, x_2) =
\begin{cases} 
1 & \text{if } x_1 \neq x_2 \\
0 & \text{if } x_1 = x_2
\end{cases}
\]

| X1 | X2 | XOR |
|----|----|-----|
| 0  | 0  | 0   |
| 0  | 1  | 1   |
| 1  | 0  | 1   |
| 1  | 1  | 0   |

## 2. Perceptron Limitation

A single-layer perceptron computes:

\[
y = 
\begin{cases} 
1 & \text{if } w_1 x_1 + w_2 x_2 + b > 0 \\
0 & \text{otherwise}
\end{cases}
\]

- It can only separate **linearly separable** data.  
- XOR is **not linearly separable**, so a single-layer perceptron **cannot solve it**.  

## 3. Solution: Multi-Layer Perceptron (MLP)

Adding a **hidden layer** with a **non-linear activation function** allows us to solve the XOR problem.

**Mathematical Formulation**

1. **Hidden layer computation:**

\[
\mathbf{h} = \sigma(\mathbf{W} \mathbf{X} + \mathbf{b})
\]

2. **Output layer computation:**

\[
y = \sigma(\mathbf{V} \mathbf{h} + c)
\]

Where:  
- \(\mathbf{X}\) is the input vector  
- \(\mathbf{W}, \mathbf{V}\) are weight matrices  
- \(\mathbf{b}, c\) are biases  
- \(\sigma\) is a non-linear activation function (e.g., `tanh` or `sigmoid`)  

**Explanation:**  
- Non-linear activations allow the network to **combine features in a non-linear way**.  
- This enables the network to learn a **non-linear decision boundary**, which is essential for solving XOR.