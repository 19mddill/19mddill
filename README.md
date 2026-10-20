# Hi, I'm Dilshad 

**Md. Dillshadul Islam** · CSE graduate (BUBT) · Bangladesh 🇧🇩

I'm building toward a **remote junior Machine Learning Engineer** role. My strongest work so far is a computer-vision thesis on classifying autism-related behaviors from video, backed by a structured study of classical ML and deep learning, plus full-stack web projects I built before moving into ML.

[![Email](https://img.shields.io/badge/Email-mddillshadul98%40gmail.com-D14836?logo=gmail&logoColor=white)](mailto:mddillshadul98@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/mddillshadul-islam-680707399)

---

##  Featured work

### [Pose-Based Autism Behavior Classification (Thesis)](https://github.com/19mddill/Autsim-Thesis)
*Team thesis (5 members, BUBT). Full LaTeX book, slides, paper and Colab notebooks are in the repo.*

Classifies five autism-related behaviors (hand flapping, finger clipping, head touching, spinning, tilting) from short video clips. We collected the clips ourselves at a special-needs school, with consent from the school and guardians.

- **Pipeline:** OpenCV frames → MediaPipe Pose (33 landmarks, 99 features/frame) → fixed 30-frame sequences, with augmentation (temporal cropping, time warping, flipping) for class imbalance.
- **Two modeling tracks:** statistical features for classical ML (Random Forest, Gradient Boosting, SVM, Logistic Regression, KNN, soft/hard voting), and raw sequences for deep learning (BiLSTM, BiGRU, CNN-BiLSTM) in TensorFlow/Keras.
- **Evaluation:** 5-fold stratified CV, held-out test set (105 clips), per-class reports, confusion matrices, one-vs-rest ROC/AUC, loss curves, SHAP for interpretability.

| Model | Test accuracy |
|-------|---------------|
| Random Forest / Hard-voting ensemble | **89.5%** |
| Gradient Boosting (chosen classical baseline) | 86.7% |
| CNN-BiLSTM (best deep model) | 84.8% |

- **Honest findings:** hand flapping is the hardest class (it often co-occurs with finger clipping and spinning). ST-GCN and optical-flow + MobileNetV2 underperformed on a dataset this small (~300 clips).
- **Scope:** a research prototype and decision-support idea, not a diagnostic tool.

### [Autism Screening Questionnaire App](https://github.com/19mddill/autism_in_toddlers)
Full-stack ML app: a React questionnaire collects 26 screening inputs (Q-CHAT-style items, demographics, history), a **Flask** API serves a **Random Forest** model, and the result page shows the screening outcome.
- Frontend: React 18, React Router, Axios, Bootstrap, JWT-based auth, deployed on GitHub Pages ([live demo](https://19mddill.github.io/autism_in_toddlers/)).
- Backend: [`autism_in_toddler_backend`](https://github.com/19mddill/autism_in_toddler_backend) (Flask, scikit-learn, pandas, trained on a ~2,000-row dataset, served as a REST `/predict` endpoint on Render).
- Screening aid only, not a diagnosis.

---

## Machine learning & deep learning study

| Repo | What's inside |
|------|---------------|
| [**Machine_Learning_Notebooks**](https://github.com/19mddill/Machine_Learning_Notebooks) | 9 notebooks following *Hands-On Machine Learning* (Géron), Ch. 1–9. An end-to-end California Housing project (best CV RMSE ≈ $42.3k, final test RMSE ≈ $41.4k), MNIST classification with threshold tuning and error analysis, Normal Equation and Batch/SGD/Mini-batch gradient descent **from scratch in NumPy**, SVMs, trees, ensembles (voting, bagging, boosting, stacking), PCA and manifold learning, K-Means, DBSCAN, Gaussian Mixtures, semi-supervised learning. |
| [**Deep_Learning_Notebooks**](https://github.com/19mddill/Deep_Learning_Notebooks) | Perceptron → MLP → Keras: Fashion-MNIST classifier (**87.3% test accuracy**), regression MLP on California Housing (test RMSE ≈ 0.54), Wide & Deep with multiple inputs and auxiliary output, subclassing API, model saving, checkpoints/early-stopping callbacks, TensorBoard, **Keras Tuner** (random search, Hyperband, Bayesian optimization), He/Glorot initialization, LeakyReLU, **Batch Normalization**. |
| [**Kaggle_Notebooks**](https://github.com/19mddill/Kaggle_Notebooks) | Titanic (in progress): EDA, title extraction from names, group-wise age imputation, fare capping, stratified sampling on a composite key. |

*These notebooks are my worked-through study of the book, with my own experiments added. Each README states this.*

---

## Full-stack web projects

| Project | Stack | Highlights |
|---------|-------|------------|
| [**freelancebangla**](https://github.com/19mddill/freelancebangla) | React, Node/Express, MySQL, JWT, Nodemailer | Freelance marketplace with separate **client** and **worker** roles, role-based middleware, job posting and applications, email flow. |
| [**ECOMMERCE-MERN**](https://github.com/19mddill/ECOMMERCE-MERN) | MongoDB, Express, React, Node | Auth with bcrypt + JWT, product/category/cart/order models, password-reset by email, **SSLCommerz** payment integration, admin dashboard. |
| [**JWT-MultiUser-Authentication-API**](https://github.com/19mddill/JWT-MultiUser-Authentication-API) | Django REST Framework, JWT | Multi-role user API, tested with Postman. |

---

## Problem solving

- [**Data-structrues-and-Algorithm**](https://github.com/19mddill/Data-structrues-and-Algorithm): a 150-problem, pattern-based roadmap for ML-engineer interviews (arrays/hashing, two pointers, sliding window, stack, and more) with solutions in Python. In progress.
- [**uvaProblems**](https://github.com/19mddill/uvaProblems): 60+ UVa solutions in C++ (data structures, graphs, number theory).

---

## Tech I use

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?logo=numpy&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikitlearn&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-D00000?logo=keras&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?logo=opencv&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?logo=flask&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?logo=django&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?logo=nodedotjs&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?logo=react&logoColor=61DAFB)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?logo=mongodb&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?logo=cplusplus&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?logo=git&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=white)
![Google Colab](https://img.shields.io/badge/Colab-F9AB00?logo=googlecolab&logoColor=white)

**ML focus:** supervised learning, model evaluation & tuning, pose-based video classification, sequence models (LSTM/GRU), ensembles, dimensionality reduction, clustering, explainability (SHAP).

---

## Education & certifications

- B.Sc. in Computer Science & Engineering, Bangladesh University of Business and Technology (BUBT)
- Python for Everybody Specialization (University of Michigan, Coursera)
- Web Applications for Everybody / Django Specialization (University of Michigan, Coursera)
- Git & GitHub, HTML5, Object-Oriented Design (Coursera)
- Back-end Development with Node.js, Express & MongoDB
- Workforce Recovery Program (Coursera, via Bangladesh Computer Council)

Certificate files and verification links: [Certificates](https://github.com/19mddill/Certificates)

---

## Right now

- Working through *Hands-On Machine Learning*, now moving from classical ML into deep learning with Keras
- Practicing data structures & algorithms for ML interviews
- Open to **remote junior ML engineer** roles and ML/data projects

## Let's talk

[mddillshadul98@gmail.com](mailto:mddillshadul98@gmail.com) ·  [LinkedIn](https://www.linkedin.com/in/mddillshadul-islam-680707399)
