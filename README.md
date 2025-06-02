# Movie-Recommender-System  
## Dataset  
This dataset consists of ratings on a scale of $1$ to $5$. The dataset has $n_u = 943$ users, and $n_m = 1682$ movies.
* Matrix $Y$ (num_movies x num_users): ratings $y^{(i,j)}$ (from 1 to 5)
* Matrix $R$: binary where $R(i,j)=1$ if user $j$ gave a rating to movie $i$, and $R(i,j)=0$ otherwise.
* Matrix $X$: each row corresponds to the feature vector $x^{(i)}$ for the i-th movie.
* Matrix $Theta$: each row corresponds to one parameter vector $\theta^{(j)}$ for the j-th user.

## Collaborative Filtering Learning Algorithm
The collaborative filtering algorithm in the setting of movie recommendations considers a set of n-dimensional parameter vectors $x^{(1)} , ..., x^{(n_m)}$ and $\theta^{(1)},...,\theta^{(n_u)}$, where the model predicts the rating for movie $i$ by user $j$ as $y^{(i,j)} = (\theta^{(j)})^T x^{(i)}$. Given a dataset that consists of a set of ratings produced by some users on some movies, you wish to learn the parameter vectors $x^{(1)},...,x^{(n_m)},\theta^{(1)},...,\theta^{(n_u)}$ that produce the best fit (minimizes the squared error).  
### Collaborative filtering cost function (without regularization)

$$ J(x^{(1)},...,x^{(n_m)},\theta^{(1)},...,\theta^{(n_u)}) = \frac{1}{2}\sum_{(i,j):r(i,j)=1}((\theta^{(j)})^T x^{(i)}-y^{(i,j)})^2$$  

### Collaborative filtering gradient (without regularization)

$$ \frac{\partial J}{\partial x_k^{(i)}} = \sum_{j:r(i,j)=1}((\theta^{(j)})^T x^{(i)}-y^{(i,j)})\theta_k^{(j)} $$

$$ \frac{\partial J}{\partial \theta_k^{(j)}} = \sum_{i:r(i,j)=1}((\theta^{(j)})^T x^{(i)}-y^{(i,j)})x_k^{(i)} $$  

### Regularized cost function

$$ J(x^{(1)},...,x^{(n_m)},\theta^{(1)},...,\theta^{(n_u)}) = \frac{1}{2}\sum_{(i,j):r(i,j)=1}((\theta^{(j)})^T x^{(i)}-y^{(i,j)})^2 +
\Big(\frac{\lambda}{2}\sum_{j=1}^{n_u}\sum_{k=1}^{n}(\theta_k^{(j)})^2 \Big) + \Big(\frac{\lambda}{2}\sum_{i=1}^{n_m}\sum_{k=1}^{n}(x_k^{(i)})^2 \Big)$$  

### Regularized gradient

$$ \frac{\partial J}{\partial x_k^{(i)}} = \sum_{j:r(i,j)=1}((\theta^{(j)})^T x^{(i)}-y^{(i,j)})\theta_k^{(j)} + \lambda x_k^{(i)}$$

$$ \frac{\partial J}{\partial \theta_k^{(j)}} = \sum_{i:r(i,j)=1}((\theta^{(j)})^T x^{(i)}-y^{(i,j)})x_k^{(i)} + \lambda \theta_k^{(j)}$$
