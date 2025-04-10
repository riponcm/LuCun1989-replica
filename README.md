# LuCun1989-replica
Replication of LeCun et al. (1989) Handwritten Digit Recognition using PyTorch. A modern implementation of the original convolutional neural network (CNN), built using PyTorch and trained on resized MNIST data. Ideal for deep learning research, educational demos, and historical benchmarking.

# 🧠 LeCun1989 CNN Replication – MNIST Handwritten Digit Recognition

This project replicates the pioneering work of **LeCun et al. (1989)**, titled *“Backpropagation Applied to Handwritten Zip Code Recognition”*, using the modern **PyTorch** deep learning framework. The goal is to faithfully reproduce the network architecture, preprocessing pipeline, and training setup — and to evaluate the impact of both the original and modern loss functions on classification performance.

---

## 📚 Original Paper

> LeCun, Y., Boser, B., Denker, J. S., Henderson, D., Howard, R. E., Hubbard, W., & Jackel, L. D. (1989).  
> *Backpropagation applied to handwritten zip code recognition*. Neural Computation, 1(4), 541–551.

---

## 📁 Project Structure

| File        | Description                                               |
|-------------|-----------------------------------------------------------|
| `V1.ipynb`  | Version 1 – Uses CrossEntropyLoss with softmax-style outputs |
| `V2.ipynb`  | Version 2 – Uses original MSELoss with bipolar targets (LeCun-style) |

---

## 🧪 Experimental Setup

### 🧠 Network Architecture (Both Versions)

- **Input**: 16×16 grayscale digit images
- **Layers**:
  - Conv1 → AvgPool → Conv2 → AvgPool
  - Flatten → FC1 (30 units) → FC2 (10 units)
- **Activation**: `tanh` throughout (as in original paper)
- **Output**: 10-class digit prediction (0–9)

### 📊 Dataset

- **Used**: [MNIST](http://yann.lecun.com/exdb/mnist/)
- **Preprocessing**:
  - Resized from 28×28 to 16×16 using bilinear interpolation
  - Normalized pixel values to [-1, 1]
  - Randomly sampled:
    - 7291 training images
    - 2007 testing images

---

## 🔀 Version Comparison

| Feature                | Version 1 (Modern)      | Version 2 (Original)    |
|------------------------|-------------------------|-------------------------|
| **Loss Function**      | CrossEntropyLoss        | MSE + bipolar targets   |
| **Output Format**      | Class indices (0–9)     | [-0.5, +0.5] per class  |
| **Target Encoding**    | One-hot (via argmax)    | Manual bipolar vectors  |
| **Train Accuracy**     | 97.93%                  | 84.25%                  |
| **Test Accuracy**      | 95.91%                  | 84.55%                  |
| **MSE (Train/Test)**   | —                       | ~0.0458 / ~0.0466       |

---

## 🎓 Goals and Motivation

This project was undertaken as part of a graduate-level study to understand the foundations of convolutional networks and benchmark historical approaches against modern standards.

Key learning outcomes:
- Reproduced and analyzed LeCun’s original architecture using modern tools
- Explored the effect of loss function choice on convergence and performance
- Demonstrated the stability of CNN principles over three decades

---

## 📈 Results

- Version 1 (CrossEntropyLoss) significantly outperforms the original loss function, validating modern best practices in classification loss design.
- Version 2 accurately replicates LeCun’s 1989 setup, providing educational insight into how early CNNs were trained and how well they generalized on structured digit tasks.

---

## 🚀 How to Run

1. Clone this repo:
   ```bash
   git clone https://github.com/riponcm/lecun1989-replica.git
   cd lecun1989-replica
   ```

2. Open in Jupyter or VSCode:
   ```bash
   jupyter notebook V1.ipynb
   jupyter notebook V2.ipynb
   ```

3. Ensure Python 3.x and the following libraries are installed:
   - `torch`
   - `torchvision`
   - `matplotlib`
   - `numpy`

---

## 📜 License

This project is open for educational and research purposes under the MIT License.

---

## 🙌 Acknowledgments

- Original research by **Yann LeCun et al.**
- MNIST Dataset: [Yann LeCun's website](http://yann.lecun.com/exdb/mnist/)
- PyTorch team for modern deep learning tools

---

## 👤 Author

**Ripon C. Malo**  
MSc in Civil Engineering (Geotechnical)  
📧 Email: riponce.buet@gmail.com  
🌐 GitHub: [riponcm](https://github.com/riponcm)
