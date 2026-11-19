# 🚀 Transformer, Made Easy

### Understand Transformer Architecture — One Step at a Time

An interactive, visual learning experience that explains how Transformer models work, from tokenization to next-word prediction.

Instead of overwhelming learners with complex mathematics and theoretical explanations, this project lets you follow a sentence through a miniature Transformer model and observe how every computation happens in real time.

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [How It Works](#-how-it-works)
- [Transformer Architecture](#-transformer-architecture)
- [Interactive Learning Experience](#-interactive-learning-experience)
- [Model Specifications](#-model-specifications)
- [Technologies Used](#-technologies-used)
- [Getting Started](#-getting-started)
- [Project Structure](#-project-structure)
- [Example Experiments](#-example-experiments)
- [Learning Objectives](#-learning-objectives)
- [Acknowledgements](#-acknowledgements)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Overview

Transformers are the foundation of modern language models such as GPT. However, understanding their internal architecture can be challenging, especially when learning about embeddings, attention mechanisms, query-key-value matrices, and probability distributions.

**Transformer, Made Easy** aims to solve this problem through an interactive educational visualization.

The project implements a small Transformer model directly in JavaScript and visualizes how input text moves through its different computational stages.

You can:
- Enter your own sentences.
- Explore tokenization and embeddings.
- Inspect Query, Key, and Value vectors.
- Visualize attention scores and attention weights.
- Compare multiple attention heads.
- Understand residual connections and feed-forward networks.
- Experiment with temperature and Top-K sampling.
- Observe next-word predictions.

The goal is to make Transformer architecture understandable through experimentation rather than memorization.

---

## ✨ Features

### 1. Interactive Tokenization
- Converts input sentences into individual tokens.
- Assigns vocabulary IDs to recognized words.
- Highlights unknown tokens.
- Displays token positions.
- Supports a vocabulary of 28 words.

### 2. Word Embeddings
- Converts token IDs into numerical vectors.
- Displays learned embedding representations.
- Visualizes positional encoding.
- Shows how embeddings and positional information combine.

### 3. Query, Key, and Value
Explore the three essential components of attention:

- **Query (Q):** Represents what a token is looking for.
- **Key (K):** Represents what a token offers.
- **Value (V):** Contains the information passed between tokens.

Inspect the matrices and resulting vectors for each attention head.

### 4. Self-Attention Visualization

Understand attention through four interactive stages:

1. Attention Scores — Calculate query-key similarity using dot products.
2. Scaling — Divide scores by the square root of the key dimension.
3. Masking — Prevent tokens from looking at future tokens.
4. Softmax — Convert scores into attention probabilities.

Visual attention connections make it easier to understand which words influence one another.

### 5. Multi-Head Attention
- Explore two independent attention heads.
- Compare their attention patterns.
- Inspect their individual outputs.
- Understand concatenation and output projection.

### 6. Feed-Forward Network
Explore what happens after attention:

- Residual connections.
- Layer normalization.
- Feed-forward transformations.
- ReLU activation.
- Second residual connection and normalization.

### 7. Next-Word Prediction

Experiment with language generation concepts:

- View prediction logits.
- Observe probability distributions.
- Adjust temperature.
- Configure Top-K sampling.
- Sample a possible next word.
- Automatically extend the input sentence.

### 8. Additional User Experience Features
- Responsive interface.
- Light and dark themes.
- Interactive vocabulary palette.
- Predefined example sentences.
- Focus-token selection.
- Numerical visualization controls.
- Reduced-motion accessibility support.

---

## 🧠 How It Works

The application follows a sentence through seven major stages.

| Stage | Operation | Purpose |
|---|---|---|
| 01 | Tokenization | Convert text into token IDs |
| 02 | Embeddings | Convert tokens into numerical vectors |
| 03 | Q, K, V | Generate attention representations |
| 04 | Self-Attention | Calculate relationships between tokens |
| 05 | Multi-Head Attention | Combine multiple attention heads |
| 06 | Feed-Forward Network | Transform contextual representations |
| 07 | Prediction | Calculate probabilities for the next word |

Each stage displays intermediate calculations so learners can understand not just what happens, but how it happens.

---

## 🏗️ Transformer Architecture

The project demonstrates a simplified decoder-style Transformer architecture.

### Overall Processing Pipeline

```text
        Input Sentence
              |
              v
         Tokenization
              |
              v
      Token Embeddings
              |
              +
      Positional Encoding
              |
              v
       Input Representations
              |
              v
     Multi-Head Self-Attention
              |
              v
       Output Projection
              |
              v
      Residual Connection
              |
              v
       Layer Normalization
              |
              v
       Feed-Forward Network
              |
              v
      Residual Connection
              |
              v
       Layer Normalization
              |
              v
       Output Projection
              |
              v
           Softmax
              |
              v
      Next-Word Prediction
```

### Important Mathematical Operations

**1. Embeddings**

Token embeddings are combined with positional encodings:

`X = Embedding + PositionalEncoding`

**2. Query, Key, and Value**

```text
Q = X × Wq
K = X × Wk
V = X × Wv
```

**3. Scaled Dot-Product Attention**

```text
Attention(Q, K, V) =
Softmax((Q × Kᵀ) / √dk + Mask) × V
```

**4. Multi-Head Attention**

```text
MultiHead =
Concat(Head1, Head2, ...) × Wo
```

**5. Feed-Forward Network**

```text
FFN(X) = W2 × ReLU(W1 × X + b1) + b2
```

**6. Next-Word Prediction**

```text
P(next word) =
Softmax((h × Wu + b) / Temperature)
```

These operations are implemented in JavaScript and their intermediate results are visualized in the browser.

---

## 🎮 Interactive Learning Experience

The application provides several ways to experiment.

### Change the Input Sentence

Try entering sentences such as:

```text
the dog chased the
```

```text
the cat chased the
```

```text
a small bird ate the
```

### Explore Attention

Select different tokens and attention heads to inspect how the model distributes attention across earlier tokens.

### Experiment with Generation

Adjust:
- Temperature: 0.1 to 2.5.
- Top-K: All words, 1, 3, or 5.

Observe how these settings affect the next-word probability distribution.

---

## 📊 Model Specifications

This project uses a deliberately small Transformer model to make its computations understandable.

| Parameter | Value |
|---|---:|
| Vocabulary Size | 28 |
| Embedding Dimension | 8 |
| Transformer Blocks | 1 |
| Attention Heads | 2 |
| Dimensions per Head | 4 |
| Feed-Forward Dimension | 16 |
| Maximum Context Length | 7 tokens |
| Number of Parameters | 1,044 |
| Training Dataset | 88 short sentences |

### Comparison with GPT-2 Small

| Parameter | This Project | GPT-2 Small |
|---|---:|---:|
| Vocabulary | 28 | 50,257 |
| Embedding Dimension | 8 | 768 |
| Attention Heads | 2 | 12 |
| Feed-Forward Dimension | 16 | 3,072 |
| Transformer Blocks | 1 | 12 |
| Context Length | 7 | 1,024 |
| Parameters | 1,044 | 124 million |

**Note:** This is an educational miniature model, not a production language model. It demonstrates the core computations using much smaller dimensions.

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| HTML5 | Application structure |
| CSS3 | Styling and responsive layout |
| JavaScript | Transformer computations and interactions |
| SVG | Attention connection visualization |
| Google Fonts | Typography |

The application performs its model computations directly in the browser.

No external machine-learning framework or backend server is required for the core functionality.

---

## 🚀 Getting Started

### Prerequisites

You only need:

- A modern web browser.
- Git.
- A code editor such as Visual Studio Code (optional).

### 1. Clone the Repository

```bash
git clone https://github.com/Programiz-007/Transformers-Learn-Easy.git
```

### 2. Navigate to the Project

```bash
cd Transformers-Learn-Easy
```

### 3. Run the Application

If the main HTML file is named `index.html`, simply open it in your browser.

Alternatively, use VS Code Live Server:

1. Open the project folder in VS Code.
2. Install the Live Server extension.
3. Right-click `index.html`.
4. Select **Open with Live Server**.

The application should now be running locally.

---

## 📁 Project Structure

The current implementation is a self-contained HTML application.

```text
Transformers-Learn-Easy/
│
├── index.html       # Application structure, styling,
│                    # Transformer model and interactions
│
└── README.md        # Project documentation
```

---

## 🧪 Example Experiments

Try these experiments to understand how attention works:

| Input | What to Explore |
|---|---|
| `the dog chased the` | Animal-dependent prediction |
| `the cat chased the` | Contextual attention |
| `a small bird ate the` | Token embeddings and prediction |
| `the happy cat sat on` | Positional information and attention |

### Suggested Experiment

Compare these two inputs:

```text
the dog chased the
```

```text
the cat chased the
```

The model was trained on a small grammar where the animal influences the expected object.

This provides a simple demonstration of why a Transformer needs to use information from earlier tokens when predicting the next word.

---

## 🎓 Learning Objectives

After exploring this project, learners should be able to:

- Understand how text is converted into tokens.
- Explain token embeddings and positional encoding.
- Understand Query, Key, and Value matrices.
- Explain scaled dot-product attention.
- Understand causal masking.
- Interpret attention weight matrices.
- Explain multi-head attention.
- Understand residual connections and layer normalization.
- Describe the role of feed-forward networks.
- Understand logits, softmax, temperature, and Top-K sampling.
- Follow the complete forward pass of a small Transformer.

---

## 🙌 Acknowledgements

This project is inspired by the educational approach of:

**[Transformer Explainer – Georgia Tech Polo Club](https://poloclub.github.io/transformer-explainer/)**

Their interactive visualization of GPT-2 helped inspire the idea of explaining Transformer computations through visual experimentation.

---

## 🤝 Contributing

Contributions, suggestions, and improvements are welcome!

If you would like to contribute:

1. Fork this repository.
2. Create a new feature branch.

```bash
git checkout -b feature/your-feature-name
```

3. Make your changes.
4. Commit your changes.

```bash
git add .
git commit -m "Add: your feature description"
```

5. Push your branch.

```bash
git push origin feature/your-feature-name
```

6. Open a Pull Request.

---

## 📄 License

A license has not yet been specified for this repository.

If you intend to make this project open source, consider adding an appropriate license file, such as the MIT License.

---

## ⭐ Support the Project

If this project helps you understand Transformer architecture, consider giving the repository a ⭐ on GitHub.

Feel free to share it with students, developers, AI enthusiasts, and anyone interested in understanding how modern language models work.

**Made with ❤️ for learning and exploring Transformers.**
