# Deep Learning Fundamentals

> **AWS AI Practitioner Exam (AIF-C01) Study Guide**

## 1. What is Deep Learning?
A subset of Machine Learning based on **Artificial Neural Networks** with multiple layers (hence "Deep"). It excels at processing unstructured data like images, audio, and text.

## 2. Neural Network Architecture
*   **Input Layer:** Receives the features.
*   **Hidden Layers:** Where the "learning" happens via weights and biases.
*   **Output Layer:** Provides the prediction.
*   **Weights:** Determine the strength of connection between neurons.
*   **Biases:** Offset added to the sum of inputs.
*   **Activation Function:** (e.g., ReLU, Sigmoid) Determines if a neuron should "fire".

## 3. How Neural Networks Learn
*   **Forward Propagation:** Passing data through the layers to get a prediction.
*   **Loss Function:** Calculates how far the prediction is from the actual label (Error).
*   **Backward Propagation (Backprop):** Calculating the gradient of the loss function.
*   **Gradient Descent:** Optimization algorithm used to update weights to minimize loss.

## 4. Common Deep Learning Architectures
| Architecture | Best For | Typical Use Case |
| :--- | :--- | :--- |
| **CNN** (Convolutional) | Visual patterns | Image recognition, Video analysis |
| **RNN** (Recurrent) | Sequential data | Speech recognition, Time series |
| **Transformers** | Contextual relationships | Natural Language Processing (LLMs) |

## 5. Key Concepts
*   **Epoch:** One full pass of the entire training dataset through the network.
*   **Batch Size:** Number of samples processed before the model is updated.
*   **Learning Rate:** How much the weights are adjusted during each step of training. (Too high = overshoots; Too low = too slow).
*   **Hyperparameter Tuning:** Finding the best learning rate, batch size, etc. (Amazon SageMaker HyperParameter Optimization - HPO).

## 6. Deep Learning vs. Traditional ML
| Feature | Traditional ML (e.g. Random Forest) | Deep Learning |
| :--- | :--- | :--- |
| **Data Requirements** | Works well with small/medium data | Requires massive datasets |
| **Feature Engineering** | Mostly manual | Automated (Feature extraction) |
| **Hardware** | CPU is often sufficient | Requires GPUs (AWS P4/P5 instances) |
| **Complexity** | Easier to interpret ("White box") | Difficult to interpret ("Black box") |

## 7. AWS Infrastructure for Deep Learning
*   **AWS Trainium:** Purpose-built chip for training deep learning models.
*   **AWS Inferentia:** Purpose-built chip for high-performance, low-cost inference.
*   **Deep Learning AMIs (DLAMI):** Pre-configured EC2 images with frameworks (PyTorch, TensorFlow).

---
*Last Updated: Jan 2026*
