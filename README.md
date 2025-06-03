# 🎬 Movie Recommender System (Item-Based Collaborative Filtering)

Welcome to my **Movie Recommender System** project!  
This system uses an item-based collaborative filtering algorithm to recommend movies that are similar to the ones a user already likes.
---

## 📊 The Dataset

- **943 users**
- **1682 movies**
- **Ratings**: Scale of 1 to 5  
  (1 = didn't like, 5 = loved it)

The data is structured using matrices:

- **Y (movies × users)**:  
  \( Y(i, j) \) is the rating that user *j* gave to movie *i*
  
- **R (movies × users)**:  
  \( R(i, j) = 1 \) if a rating exists, 0 if not

- **X (movies × features)**:  
  Each row is a feature vector for a movie

- **Θ (users × features)**:  
  Each row is a user’s parameter vector — capturing user preferences

Together, these matrices help estimate missing ratings and generate recommendations.

---

## ⚙️ How I Built It

### 1. **Preprocessing**
- Loaded and structured the dataset
- Constructed matrices \( Y \) and \( R \)
- Normalized ratings to handle user rating biases

### 2. **Collaborative Filtering Logic**
- Used item similarity (via feature vectors in matrix \( X \)) to calculate closeness between movies
- Predicted how much a user might like an unseen movie
- Applied vectorized cost functions and gradient computations to optimize parameters

### 3. **Training the Model**
- Optimized parameters \( X \) and \( Θ \) using regularized cost functions
- Iteratively minimized prediction error using gradient descent

### 4. **Making Recommendations**
- For any user, identified movies they haven’t rated
- Recommended top movies with the highest predicted ratings

---

## 📌 Key Concepts Used

- **Collaborative Filtering**
- **Matrix Factorization**
- **Gradient Descent Optimization**
- **Vectorized Implementation with NumPy**
- **Mean Normalization of Ratings**
- **Regularization to Prevent Overfitting**

---

## 🚀 Getting Started

Follow these steps to set up and run this project on your local machine.

### 📁 Prerequisites

- Python 3.x installed
- `pip` (Python package manager)

---

### ⚙️ Step-by-Step Setup

1. **Clone the Repository**
   ```bash
   git clone https://github.com/AryaHaldankar/Movie-Recommender-System/.git
   cd Movie-Recommender-System

2. **Create a virtual environment**
   ```bash
   python -m venv venv

3. **Activate the Virtual Environment**  
   ***- On Windows***
   ```bash
   venv\Scripts\activate
   ```  
  ***- On Mac/Linux***
  ```bash
  source venv/bin/activate
  ```
4. **Install Project Dependencies**
   ```bash
   pip install -r requirements.txt
   
5. **Add the `data/` Folder**

   Download the `data` folder from the provided link [Drive Link](https://drive.google.com/drive/folders/10VLLqmoMUGGbMM590s9thchlIkT7ps0e?usp=sharing).

   Place the entire `data/` folder inside the root of the project directory — the same directory where your scripts and `requirements.txt` are located.
6. **Run Script**
   ```bash
   python3 Movie-Recommender-System.py
