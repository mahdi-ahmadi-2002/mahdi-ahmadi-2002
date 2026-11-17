<h1 align="center">Hi, I'm Mahdi Ahmadi 👋</h1>

<p align="center">
  <b>AI / Machine Learning Engineer</b> &nbsp;·&nbsp; M.Sc. Computer Science student at <b>TU Berlin</b><br>
  Speech &amp; audio · Computer vision · NLP &amp; LLMs, plus the backend skills to ship them.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Open_to-Working_Student_(Werkstudent)_roles-2ea44f?style=for-the-badge" alt="Open to working student roles">
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/mahdi-ahmadi-3b75ab287"><img src="https://img.shields.io/badge/LinkedIn-Mahdi_Ahmadi-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:m.ahmadi@campus.tu-berlin.de"><img src="https://img.shields.io/badge/Email-m.ahmadi%40campus.tu--berlin.de-D14836?style=flat-square&logo=gmail&logoColor=white" alt="Email"></a>
  <img src="https://img.shields.io/badge/Based_in-Berlin,_Germany-555?style=flat-square&logo=googlemaps&logoColor=white" alt="Berlin">
</p>

---

## 🧠 About me

- 🎓 **M.Sc. Computer Science at TU Berlin** (since 04/2026). B.Sc. in Computer Science from Shahid Beheshti University, **top 10%** of the department.
- 🤖 **I build deep-learning systems end to end:** data pipeline, model, evaluation against real baselines, and a tested package that other people can run.
- 🔊 **Main areas:** speech and audio enhancement, computer vision, and NLP/LLM applications (GPT integration, RAG).
- ⚙️ **I also have backend experience:** a 10-month developer internship building REST APIs on PostgreSQL. A model only matters once it is served, tested and deployed.
- 🧑‍🏫 Teaching assistant for **8 university courses**, including Artificial Neural Networks and Foundations of Machine Learning (graduate level).
- 💼 **Looking for:** a working-student (Werkstudent) or student-assistant role in **AI / ML** in Berlin. Available **now**, 15–20 hours per week.

---

## 📊 Highlights

<table>
  <tr>
    <td align="center" width="25%"><h3>+10.9 dB</h3>speech-quality gain (SI-SDR) on unseen speakers: <b>2×</b> a classical Wiener filter</td>
    <td align="center" width="25%"><h3>≈ 0.5 m/s</h3>mean error estimating vehicle speed from dashcam video alone</td>
    <td align="center" width="25%"><h3>56× faster</h3>full-text search on 200k rows after index design (63 ms → 1.1 ms)</td>
    <td align="center" width="25%"><h3>97%</h3>test coverage on a production-style async API (107 tests, CI)</td>
  </tr>
</table>

---

## 🚀 Featured AI projects

### 🔊 [Speech Enhancement with an Attention U-Net](https://github.com/mahdi-ahmadi-2002/Unet-Audiomnist-Denoiser)
<img align="right" width="420" src="https://raw.githubusercontent.com/mahdi-ahmadi-2002/Unet-Audiomnist-Denoiser/master/results/si_sdr_by_noise.png" alt="SI-SDR improvement by noise type">

A single-channel speech enhancer: an attention U-Net predicts a **phase-aware time-frequency mask** on the STFT. I compared it with classical DSP baselines that I implemented myself.

- **SI-SDR 6.0 → 16.9 dB** and **STOI 0.883 → 0.947** on 3,000 utterances from **six held-out speakers**
- About **2× the gain** of spectral subtraction and a Wiener filter, and **~10× faster than real time** on a CPU
- Five noise types (white, pink, brown, mains hum, babble) at −5 to 20 dB SNR, with results broken down by noise type, SNR and speaker group
- Packaged with configs, an inference CLI, a **Gradio demo**, **54 tests** and CI

`PyTorch` `STFT` `DSP` `SI-SDR / STOI` `Gradio`

<br clear="right"/>

### 🚗 [Vehicle Speed Estimation from Dashcam Video](https://github.com/mahdi-ahmadi-2002/Vehicle-Speed-Estimation)
<img align="right" width="320" src="https://raw.githubusercontent.com/mahdi-ahmadi-2002/Vehicle-Speed-Estimation/master/results/demo.gif" alt="Speed estimation demo">

Estimates a car's speed using only its forward-facing camera (comma.ai speed challenge).

- **Validation MSE 0.51 (m/s)²** vs. 70.94 for a constant-speed baseline
- Three estimators compared: a **one-parameter ground-plane geometry model**, a **flow CNN**, and a **streaming CNN + GRU**
- **Kalman filter** for live use and an **RTS smoother** for offline use
- A **leakage-free time-block split**, plus a write-up of why the first version always predicted the same speed

`PyTorch` `OpenCV` `Optical flow` `Kalman filtering`

<br clear="right"/>

### 🎨 [Landscape → Painting with CycleGAN](https://github.com/mahdi-ahmadi-2002/Style-Transfer-Landscape2Art)

CycleGAN **implemented from scratch** (ResNet-9 generators, 70×70 PatchGAN, LSGAN, cycle and identity losses). It translates about 4.3k landscape photos into **seven WikiArt styles** without paired data. Training survives Kaggle session limits (mixed precision, automatic resume), and a CI smoke test runs every notebook cell.

<p align="center">
  <img width="90%" src="https://raw.githubusercontent.com/mahdi-ahmadi-2002/Style-Transfer-Landscape2Art/master/assets/naive_cycle.jpg" alt="Photo to Naive Art and back">
</p>

`PyTorch` `GANs` `Unpaired image translation` `FID`

### 🧾 [Code Summarization: PLBART vs. CodeT5](https://github.com/mahdi-ahmadi-2002/CodeBART-Code-Summarization)

Fine-tunes two pre-trained code transformers to write docstring summaries for Python functions (CodeXGLUE, 252k training functions). Both models use the same pipeline, so the comparison is fair. The project includes an explicit **data-leakage audit**: docstring-free inputs, pre-trained-only checkpoints, and a single pass over the test set. Models are selected on validation BLEU and decoded with beam search.

`Hugging Face Transformers` `Seq2seq` `BLEU / ROUGE`

---

## ⚙️ The backend side

### 📝 [FastAPI-Blog: an async REST API built like production](https://github.com/mahdi-ahmadi-2002/FastAPI-Blog)
<img align="right" width="380" src="https://raw.githubusercontent.com/mahdi-ahmadi-2002/FastAPI-Blog/master/docs/screenshots/app-home.png" alt="FastAPI-Blog web app">

- **35+ endpoints** with FastAPI, SQLAlchemy 2, PostgreSQL and Redis
- JWT authentication with **rotating refresh tokens and reuse detection**, plus Argon2id password hashing and rate limiting
- Full-text search **63 ms → 1.1 ms** with a GIN index; keyset pagination for the feed
- **107 tests, 97% coverage** against a real PostgreSQL database; CI runs linting, strict type checks and migration round-trips
- One-command start with `docker compose up` (API, database, Redis, React frontend)

`FastAPI` `PostgreSQL` `Redis` `Docker` `GitHub Actions`

<br clear="right"/>

---

## 🧪 More projects

| Project | What it shows |
|---|---|
| [Spoken-Digit Recognition](https://github.com/mahdi-ahmadi-2002/MNIST_Audio_processing) | CNN, LSTM and Transformer on log-mel spectrograms: **99.2–99.7%** accuracy on AudioMNIST |
| [ViT vs. ResNet50](https://github.com/mahdi-ahmadi-2002/ViT-RESNET-CIFAR10) | Fine-tuned ResNet50 reaches **93.9%** on CIFAR-10 vs. 51.2% for a ViT trained from scratch |
| [Multi-Task Autoencoder](https://github.com/mahdi-ahmadi-2002/Multi-Task-Image-Reconstruction-Autoencoder) | Dual-decoder CNN that separates blended CIFAR-10/MNIST images (**27.2 dB PSNR**) |
| [Cat Facial Keypoints](https://github.com/mahdi-ahmadi-2002/Cat-Facial-Keypoint-Detection) | ResNet50 + Feature Pyramid Network regressing nine facial landmarks |
| [Classical Computer Vision](https://github.com/mahdi-ahmadi-2002/Basic-computer-vision-methods) | SIFT/HOG matching, Hough lane detection, filtering and histogram methods from scratch |

---

## 💼 Experience

| Role | Where | When |
|---|---|---|
| **Research Assistant, Applied AI**: integrated GPT models into a speech-based interview agent and a RAG assistant for legal and contract questions | Dr. A. Katanforoush's Lab, Shahid Beheshti University | 06/2024 – 10/2025 |
| **Junior Developer Intern**: FastAPI/Flask REST APIs, migration of reporting to async Python, PostgreSQL query and index optimization | MTN Irancell, Tehran | 07/2024 – 04/2025 |
| **Research Assistant, Computational Neuroscience**: learnable firing thresholds for spiking neural networks (became my B.Sc. thesis) | Dr. S. R. Kheradpisheh's Lab, Shahid Beheshti University | 06/2024 – 07/2025 |
| **Teaching Assistant**: 8 courses, incl. Artificial Neural Networks and Foundations of ML (graduate) | Shahid Beheshti University | 2022 – 2025 |

📄 **Publication (under review):** *Tackling Class Imbalance and Overlap Challenges in Stroke Prediction with Deep Learning Algorithms*, Neural Computing and Applications.

---

## 🛠️ Tech stack

**AI / ML**<br>
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging_Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=flat-square&logo=scipy&logoColor=white)
![librosa](https://img.shields.io/badge/librosa-audio-4B8BBE?style=flat-square)
![OpenAI API](https://img.shields.io/badge/GPT_API_%2F_RAG-412991?style=flat-square&logo=openai&logoColor=white)

**Backend &amp; data**<br>
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?style=flat-square&logo=sqlalchemy&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)

**Engineering &amp; tools**<br>
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![LaTeX](https://img.shields.io/badge/LaTeX-008080?style=flat-square&logo=latex&logoColor=white)

---

## 🌍 Languages

English: **C1** (IELTS 7.5) &nbsp;·&nbsp; German: **A2** (learning) &nbsp;·&nbsp; Persian: **native**

---

<p align="center">
  <b>Hiring for an AI / ML working-student role in Berlin?</b><br>
  I'd be glad to talk: <a href="mailto:m.ahmadi@campus.tu-berlin.de">m.ahmadi@campus.tu-berlin.de</a> · <a href="https://www.linkedin.com/in/mahdi-ahmadi-3b75ab287">LinkedIn</a>
</p>
