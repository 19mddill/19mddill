# Hi, I'm Dilshad

**Md. Dillshadul Islam** - CSE graduate (BUBT), GPA:3.9/4.0 - Bangladesh 🇧🇩

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

A structured, code-first study of *Hands-On Machine Learning* (Géron). I ran every experiment myself, read the outputs, and added my own variations. The numbers below come straight from the notebook outputs. Click a repo to expand the details.

| Repo | Focus | Headline results |
|------|-------|------------------|
| [**Machine_Learning_Notebooks**](https://github.com/19mddill/Machine_Learning_Notebooks) | Classical ML, Ch. 1–9 (9 notebooks) | Housing test RMSE ≈ $41.4k · MNIST "5-detector" at 0.98 precision / 0.91 recall · PCA keeps 95% of MNIST variance with 154 of 784 features |
| [**Deep_Learning_Notebooks**](https://github.com/19mddill/Deep_Learning_Notebooks) | Neural networks with Keras / TensorFlow (2 notebooks) | Fashion-MNIST test accuracy 87.3% · housing MLP test RMSE ≈ 0.54 · three hyperparameter-search strategies compared |
| [**Kaggle_Notebooks**](https://github.com/19mddill/Kaggle_Notebooks) | Competition-style data prep | Titanic EDA and feature engineering (modeling still to come) |


<summary><b> Machine_Learning_Notebooks: all 9 notebooks in detail</b></summary>

<br>

| # | Notebook | What I did | Key numbers |
|---|----------|------------|-------------|
| 1 | `lifeSatisfaction` | Model-based vs instance-based learning: `LinearRegression` vs `KNeighborsRegressor(k=3)` on GDP vs life-satisfaction data. | Same new country: 6.30 (linear) vs 6.33 (3-NN) |
| 2 | `california_housing` | **End-to-end regression project.** EDA and correlation analysis, income-stratified split (compared with a random split), engineered ratio features, a `ColumnTransformer` pipeline (median imputation, log transforms, scaling, one-hot, KMeans-based geographic-similarity features), model comparison with cross-validation, `RandomizedSearchCV`, feature-importance analysis, final test evaluation. | Linear regression train RMSE ≈ $68,973 (underfits) · decision tree train $0 vs CV ≈ $66,551 (overfits) · tuned Random Forest CV ≈ $42,250 · **final test RMSE ≈ $41,446**. My experiment: dropping low-importance features gave no gain (≈ $42.4k), so I kept all features. |
| 3 | `classfication` | **MNIST classification.** Binary "5 detector" with SGD and Random Forest, confusion matrix, precision/recall curves, threshold selection, ROC/AUC. Multiclass with OvR, OvO, SVC and scaled SGD. Error analysis (normalized confusion matrices, 3-vs-5 study). Multilabel, `ClassifierChain`, and multioutput **image denoising** with k-NN. | Dummy baseline 90.97% accuracy (why accuracy misleads) · SGD ROC AUC 0.960 · at 90% precision recall falls to 48% · Random Forest at threshold 0.44: precision 0.981, recall 0.906, F1 0.942 · multilabel k-NN macro F1 0.976 |
| 4 | `linear_model_training_principles` | **Training from scratch in NumPy:** Normal Equation, SVD/`lstsq`, Batch, Stochastic and Mini-batch Gradient Descent, learning-rate schedules, checked against scikit-learn. Polynomial regression, learning curves (under/overfitting), Ridge, Lasso, Elastic Net (including CV variants), early stopping, Logistic and Softmax regression on Iris. | Recovers θ ≈ (4.21, 2.77) from data generated with (4, 3), matching scikit-learn |
| 5 | `SVM` | Linear SVM with scaling, polynomial features + `LinearSVC`, polynomial and Gaussian RBF kernels on moons (effect of `degree`, `coef0`, `gamma`, `C`), and SVM **regression** (`LinearSVR`, kernelized `SVR`, effect of ε and C). | Visual decision-boundary comparisons |
| 6 | `decision_trees` | Training and visualizing trees on Iris (Graphviz export, class probabilities), regularization with `max_depth` / `min_samples_leaf`, `DecisionTreeRegressor` on noisy quadratic data, and a PCA-rotation experiment showing trees' sensitivity to feature orientation. | Moons test accuracy: 90.1% unregularized → 91.8% with `min_samples_leaf=5` |
| 7 | `ensemble_learning_and_random_forest` | Hard vs soft voting (soft-vote averaging worked through by hand), bagging with out-of-bag scoring, Random Forest and feature importances (Iris, plus a pixel-importance heatmap on MNIST), AdaBoost, **Gradient Boosting built by hand** (fitting trees to residuals), early stopping, `HistGradientBoostingRegressor`, Stacking. | Voting 0.904 (hard) / 0.920 (soft) · bagging 0.920 · AdaBoost 0.88 · **stacking 0.928** · boosting early-stopped at 102 trees · HistGB on housing CV RMSE ≈ $47.6k |
| 8 | `Dimensionality_Reduction` | PCA by hand via SVD and with scikit-learn, choosing components by explained variance, PCA + Random Forest tuned jointly with `RandomizedSearchCV`, `IncrementalPCA` with memory-mapped arrays, Gaussian and sparse random projection (Johnson–Lindenstrauss bound, sparse matrix built by hand), manifold learning (LLE, MDS, Isomap, t-SNE) on a Swiss roll. | **154 of 784 components keep 95% of MNIST variance** · best tuned pipeline used 57 components (on a 1,000-sample subset) |
| 9 | `unsupervised_learning` | K-Means and Mini-batch K-Means (elbow, silhouette), **color-quantization image segmentation**, **semi-supervised learning** (representative samples, label propagation), DBSCAN (+ k-NN on top for prediction), Gaussian Mixtures (covariance types, BIC/AIC, density-based **anomaly detection**), Bayesian Gaussian Mixtures. | Silhouette 0.627 on 5 blobs · digits accuracy: 50 random labels **75.8%** → 50 cluster representatives **81.9%** → label propagation **87.4%** |




<summary><b> Deep_Learning_Notebooks: Keras / TensorFlow in detail</b></summary>

<br>

**`ANN_keras.ipynb`: from perceptron to tuned networks**

| Experiment | Setup | Result |
|------------|-------|--------|
| Perceptron (Iris) | scikit-learn `Perceptron` on petal length/width (setosa vs rest, versicolor vs rest), decision boundary computed from the learned weights | Shows what a single neuron can and can't separate |
| Baseline MLP | scikit-learn `MLPRegressor` (3×50) in a scaling pipeline | Reference before moving to Keras |
| Fashion-MNIST classifier | Keras Sequential 784 → 300 → 100 → 10 (ReLU, softmax), SGD, 30 epochs, 55k train / 5k validation | Train 92.4% · val 87.5% · **test 87.3%** (the train-validation gap shows mild overfitting) |
| Regression MLP | California Housing, `Normalization` layer + 3×50 ReLU + 1 output, Adam, 20 epochs | **Test RMSE ≈ 0.54** (target is in $100k units, ≈ $54k) |
| Wide & Deep | Functional API with two inputs (5 "wide" and 6 "deep" feature subsets), shared output | Test RMSE ≈ 0.578 |
| Auxiliary output | Same model plus an auxiliary head as a regularizer | Main-output test RMSE ≈ 0.572 (aux head 0.621) |
| Subclassing API | Wide & Deep rebuilt as a `tf.keras.Model` subclass | Same architecture, custom class |

**Production-style workflow:**
- **Saving and loading:** `model.export()` (SavedModel), reloaded through `TFSMLayer`; weights saved/loaded as `.weights.h5`.
- **Callbacks:** `ModelCheckpoint` (weights only) and `EarlyStopping(patience=10, restore_best_weights=True)`.
- **TensorBoard:** run directories with profiling enabled.

**Hyperparameter search with Keras Tuner** (Fashion-MNIST, 10 epochs per trial). Search space: 0–8 hidden layers, 16–256 neurons, learning rate 1e-4 to 1e-2 (log scale), SGD vs Adam, and a tunable normalization step in a custom `HyperModel`.

| Strategy | Trials | Time | Best validation accuracy |
|----------|--------|------|--------------------------|
| Random search | 5 | ≈ 6 min | 84.4% |
| Bayesian optimization | 10 | ≈ 10 min | 86.3% |
| Hyperband | 60 | ≈ 30 min | 86.8% |

**`training_DNN_Keras.ipynb`: training deep networks**
- Weight initialization: He normal and a custom `VarianceScaling` (Glorot-style) initializer.
- Activations: ReLU vs **LeakyReLU**.
- **Batch Normalization** in a 784-300-100-10 network: 271,346 parameters in total, of which 2,368 are non-trainable (the moving mean and variance), and I inspected which BatchNorm variables are trainable (γ, β) and which are not (moving mean and variance).

**What I took away from it:**
- On this tabular dataset, my tuned Random Forest (≈ $41k RMSE) beat the neural network (≈ $54k). The splits differ between the two notebooks, so this is a rough comparison, but it matches the common experience that tree ensembles are hard to beat on tabular data.
- Tuned searches under a 10-epoch budget (best 86.8%) did not beat my hand-built 30-epoch baseline (87.5% validation), a reminder that training budget matters as much as search strategy.


<summary><b> Kaggle_Notebooks: Titanic (in progress)</b></summary>

<br>

- Exploratory analysis of the Titanic dataset.
- Feature engineering: **title extraction** from passenger names, **group-wise age imputation**, fare capping.
- **Stratified sampling on a composite key.**
- Modeling and leaderboard submission are the next step.



*These notebooks are my worked-through study of Géron's book, with my own experiments added.*

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

- B.Sc. in Computer Science & Engineering, GPA: 3.9/4.0,Bangladesh University of Business and Technology (BUBT)
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
