<div align="center">

<!-- Animated SVG banner — place header.svg in repo root -->
<img src="header.svg" width="100%" alt="AI & ML for Geoscientists"/>

<br/>

![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--Learn-ML-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Status](https://img.shields.io/badge/Status-Actively%20Drilling-e94560?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-a8edea?style=for-the-badge)

<br/>

> *"A geoscientist who can code is dangerous.*
> *A geoscientist who knows ML is unstoppable.*
> *A geoscientist who does both? They probably run the whole field by Thursday."*
>
> — Anonymous (possibly a geoscientist in denial about Python)

</div>

---

## 🤔 Why Should a Geoscientist Learn AI?

Great question. Short answer: **because the oil isn't going to find itself.**

| Without AI 😭 | With AI 🚀 |
|---|---|
| Eyeballing well logs at 3am ☕ | ML finds the pattern in milliseconds |
| Excel spreadsheets with 47 tabs | Pandas DataFrames that actually make sense |
| "I think this is a good zone…" | Confidence intervals and model predictions |
| Manual seismic interpretation | Automated fault detection with CNNs |
| Copy-paste reports forever | Auto-generated insights in seconds |

---

## 📚 Course Content

Think of this as **geological strata** — we drill from the surface all the way down to the neural network basement. 🪨➡️🤖

---

### 🌍 Layer 1 — The Big Picture: Data Science & ML

> *Before writing a single line of code, let's make sure we're not just nodding along to buzzwords.*

- 📌 What is Data Science?
- 📌 What is Machine Learning?
- 📌 Brief History of Data Science
- 📌 Data Analysis vs Data Analytics
- 📌 Data Science vs Machine Learning
- 📌 Why learn to code? (spoiler: it's worth it)
- 📌 Data Science Knowledge Domains
- 📌 The Data Science Life Cycle
- 📌 Data Science Skills You Actually Need

---

### 🐍 Layer 2 — Learning Python (Yes, You Can Do This)

> *Python is not hard. It's basically English with brackets. Promise.*

- 🐍 Why Python? (and not MATLAB, R, or interpretive dance)
- 🐍 Programming concepts & coding workflow
- 🐍 Which language should you start with?
- 🐍 How to actually write and run code

---

### 📊 Layer 3 — The PyData Stack (Your New Best Friends)

> *The holy trinity of scientific Python. Master these and you can wrangle any dataset on the planet.*

| Library | What it does | Geo use case |
|---|---|---|
| 🔢 **NumPy** | Fast numerical & array operations | Matrix operations on seismic volumes |
| 🐼 **Pandas** | DataFrame magic | Well log data tables |
| 📈 **Matplotlib** | Plotting everything | Cross-sections, log tracks |
| 🌊 **Seaborn** | Beautiful statistical plots | Facies distribution charts |

---

### 🪨 Layer 4 — Geoscience-Specific Libraries

> *Finally — libraries made **for us**, by people who have also cried over bad LAS files.*

```python
import lasio        # Read LAS well log files without crying
import welly        # Work with wells like a pro
import segyio       # Tame seismic SEG-Y data
```

- 🛢️ **Welly + LASIO** — Well log I/O and manipulation
- 📡 **SEGYIO** — SEG-Y seismic data handling

---

### 🤖 Layer 5 — Machine Learning: The Main Event

> *This is where the magic (and occasional confusion) happens.*

#### Supervised ML 🎯
Learn from labelled data — like a student who actually studied for the exam.

| Algorithm | Nickname | Geo Application |
|---|---|---|
| Linear Regression | `LM` | Porosity-depth trends |
| Logistic Regression | `LR` | Facies classification (binary) |
| Support Vector Machine | `SVM` | Lithology prediction |
| Random Forest | `RF` | Multi-facies classification |

#### Unsupervised ML 🕵️
Finds patterns with no labels — like a detective with no witnesses.

| Algorithm | Nickname | Geo Application |
|---|---|---|
| K-Means Clustering | `K-Means` | Electrofacies grouping |
| Principal Component Analysis | `PCA` | Dimensionality reduction of logs |

#### Neural Networks 🧠
The fancy stuff. Works. Takes more data to understand why it works.
- Theory: what neurons, layers, and activation functions actually mean
- Application: real geoscience examples with code

---

## 🧰 Your Toolkit

Everything below is **free and open-source**. We love open source. Open source never ghosted us.

```
✅ Python 3.8+
✅ Jupyter Notebook / JupyterLab
✅ NumPy · Pandas · Matplotlib · Seaborn
✅ LASIO · Welly · SEGYIO
✅ Scikit-learn
✅ TensorFlow or PyTorch (for the neural net fun)
```

---

## 🎒 Prerequisites

| Requirement | Details |
|---|---|
| 🪨 Geoscience background | You've seen a well log. That counts. |
| 💻 A computer | Borrowed laptops are fine. We don't judge. |
| 🧠 Curiosity | Willingness to Google error messages at 11pm |
| 🐍 Coding experience | **Zero needed.** Seriously. None. |
| ☕ Coffee | Optional but strongly recommended |

---

## 🚀 Getting Started

```bash
# 1. Clone this repo
git clone https://github.com/YOUR_USERNAME/aiml-for-geoscientists.git
cd aiml-for-geoscientists

# 2. Install dependencies
pip install numpy pandas matplotlib seaborn scikit-learn lasio welly segyio jupyter

# 3. Launch Jupyter
jupyter notebook

# 4. Open Module 1 and begin your journey 🌋
```

---

## 📁 Repo Structure

```
📦 aiml-for-geoscientists/
├── 📂 01_data_science_intro/
├── 📂 02_python_basics/
├── 📂 03_pydata_stack/        # NumPy, Pandas, Matplotlib, Seaborn
├── 📂 04_geoscience_libs/     # Welly, LASIO, SEGYIO
├── 📂 05_machine_learning/
│   ├── 📂 supervised/         # LR, LM, SVM, RF
│   ├── 📂 unsupervised/       # K-Means, PCA
│   └── 📂 neural_networks/    # The brain stuff 🧠
├── 📂 datasets/               # Sample well logs & seismic data
├── 📂 notebooks/              # All Jupyter notebooks
└── 📜 README.md
```

---

## 🤝 Contributing

Found a bug? Have a better geo example? Know a funnier joke about porosity?

**Pull requests are welcome!** 🎉

```
1. Fork the repo
2. Create your branch: git checkout -b feature/better-facies-joke
3. Commit: git commit -m "Add actually funny log interpretation pun"
4. Push & open a PR
```

---

## 📜 License

MIT — do whatever you want, just don't blame us if your neural net predicts oil where there is none. 🛢️❌

---

<div align="center">

Made with ❤️ + 🪨 + too much ☕ by geoscientists, for geoscientists

*No rocks were harmed in the making of this course.*

⭐ **Star this repo if it helped you!** ⭐

</div>
