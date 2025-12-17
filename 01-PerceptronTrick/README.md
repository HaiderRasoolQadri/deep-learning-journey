# The Perceptron Trick

The **Perceptron** is one of the simplest linear classifiers and a foundational building block of neural networks. The **Perceptron Trick** refers to its **weight update rule**, which ensures learning only happens on misclassified points.

## 1. Intuition

- Imagine you are trying to separate two groups of points on a 2D plane using a straight line.  
- The Perceptron adjusts the line **only when it makes a mistake** on a point.  
- Correctly classified points do **not** affect the line.  
- Over time, the line rotates and shifts to separate the points perfectly (if they are linearly separable).

**Key idea:** "Only fix mistakes, don’t touch correct classifications."

## 2. Mathematical Working

Given:

- Input vector: \( \mathbf{x} = [x_1, x_2, ..., x_n]^T \)  
- Label: \( y \in \{-1, +1\} \)  
- Weights: \( \mathbf{w} \)  
- Bias: \( b \)  

The prediction is:

\[
\hat{y} = \text{sign}(\mathbf{w} \cdot \mathbf{x} + b)
\]

The **decision boundary**:

\[
\mathbf{w} \cdot \mathbf{x} + b = 0
\]

**Perceptron Weight Update (The Trick)**

If a point is misclassified:

\[
y_i (\mathbf{w} \cdot \mathbf{x}_i + b) \le 0
\]

Update weights and bias as:

\[
\mathbf{w} \leftarrow \mathbf{w} + \eta y_i \mathbf{x}_i
\]

\[
b \leftarrow b + \eta y_i
\]

Where:

- \( \eta > 0 \) is the learning rate  
- \( y_i \mathbf{x}_i \) "pushes" the decision boundary toward correct classification  

**Why it works:**  

- Misclassified points “pull” the boundary toward themselves  
- Correct points are ignored, preventing unnecessary adjustments  
- Guarantees convergence if data is linearly separable  

## 3. Algorithm (Step by Step)

1. **Initialize** weights \( \mathbf{w} = 0 \) and bias \( b = 0 \)  
2. For each **epoch** (loop over dataset):  
   - For each sample \( (\mathbf{x}_i, y_i) \):  
     1. Compute prediction: \( \hat{y}_i = \text{sign}(\mathbf{w} \cdot \mathbf{x}_i + b) \)  
     2. If misclassified (\( y_i \hat{y}_i \le 0 \)):  
        \[
        \mathbf{w} \leftarrow \mathbf{w} + \eta y_i \mathbf{x}_i
        \]  
        \[
        b \leftarrow b + \eta y_i
        \]  
3. Repeat until convergence or maximum epochs reached  

## 4. Limitations

1. **Linearly Separable Only:**  
   - If classes cannot be separated by a straight line, the algorithm never converges.  

2. **Sensitive to Outliers:**  
   - A single misclassified outlier can cause large weight updates.  

3. **No Probabilistic Output:**  
   - Only provides hard classifications (\(-1\) or \(+1\)), no confidence scores.  

4. **Cannot Capture Complex Patterns:**  
   - Non-linear boundaries require extensions like **kernel trick** or **multi-layer networks**.  
