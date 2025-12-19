# The Problem / Limitation

The main problem with the perceptron (and its “tricks”) is:

## 1.Linearly separable data requirement

- The basic perceptron only converges if the data is linearly separable.
- If the classes cannot be separated by a straight line (or hyperplane), the perceptron never converges.

## 2. Cannot model nonlinear patterns

- XOR is the classic example. No matter what “trick” you use (like adding a bias), a single-layer perceptron cannot represent XOR.

- Solution: multilayer perceptrons (MLPs) with nonlinear activation functions.

## 3. Sensitive to scaling

- Learning depends on the magnitude of input features.
- Normalization is often needed, or else the updates can be unstable.