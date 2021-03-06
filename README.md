<div align="center">
	<a href="https://github.com/gov-ai/ProML/tree/main">
		<img src="header.svg" width="800" height="400" alt="Click to see the source">
	</a>
</div>

<br>
<br>

# ProML

### 1. Supervised Learning


#### 1.1.1. Ordinary Least Square 

> **Detour**
> - [SSR, SSE & SST Explained visually](https://excalidraw.com/#json=vhWfaD5v_fdHjDh8oBtaS,mLix-LNId2pfmu0gVll5DQ)
> - [Good blog / read on R-squared score and Adj. R-squared score](https://365datascience.com/tutorials/statistics-tutorials/r-squared/)
>   - When should we <span style="color: red;">not</span> use R sq. score?
>   - When should we use Adj. R Sq. score?
> - [Bending a linear regression line using polynomial feaures & bias-variance tradeoff](https://scikit-learn.org/stable/auto_examples/model_selection/plot_underfitting_overfitting.html)

```mermaid
classDiagram
  class ndarray {
   ...
  }
  class BaseEstimator {
    feature_names_in_ : NoneType
    n_features_in_
    get_params(deep)
    set_params()
  }
  class MultiOutputMixin {
  }
  class RegressorMixin {
    score(X, y, sample_weight)
  }
  class LinearModel {
    coef_
    intercept_ : float
    fit(X, y)
    predict(X)
  }
  class LinearRegression {
    coef_ : list
    copy_X : bool
    fit_intercept : bool
    n_jobs : NoneType
    normalize : str
    positive : bool
    rank_
    singular_
    fit(X, y, sample_weight)
  }
  LinearModel --|> BaseEstimator
  LinearRegression --|> MultiOutputMixin
  LinearRegression --|> RegressorMixin
  LinearRegression --|> LinearModel
  ndarray --* ndarray : T
  ndarray --* LinearRegression : coef_
  ndarray --* LinearRegression : coef_
  ndarray --* LinearRegression : _residues
```

#### 1.1.2. Ridge Regression

```mermaid
classDiagram
  class ndarray {
    ...
  }
  class BaseEstimator {
    feature_names_in_ : NoneType
    n_features_in_
    get_params(deep)
    set_params()
  }
  class MultiOutputMixin {
  }
  class RegressorMixin {
    score(X, y, sample_weight)
  }
  class LinearModel {
    coef_
    intercept_ : float
    fit(X, y)
    predict(X)
  }
  class Ridge {
    fit(X, y, sample_weight)
  }
  class _BaseRidge {
    alpha : float
    coef_
    copy_X : bool
    fit_intercept : bool
    intercept_
    max_iter : NoneType
    n_iter_ : NoneType
    normalize : str
    positive : bool
    random_state : NoneType
    solver : str
    tol : float
    fit(X, y, sample_weight)
  }
  LinearModel --|> BaseEstimator
  Ridge --|> MultiOutputMixin
  Ridge --|> RegressorMixin
  Ridge --|> _BaseRidge
  _BaseRidge --|> LinearModel
  ndarray --* _BaseRidge : coef_
  ndarray --* _BaseRidge : coef_
  ndarray --* _BaseRidge : n_iter_
  ndarray --* _BaseRidge : n_iter_
  ndarray --* _BaseRidge : n_iter_
  ndarray --* _BaseRidge : intercept_
```

#### 1.1.3. Lasso Regression

```mermaid
classDiagram
  class ndarray {
    ...
  }
  class ndarray {
    ...
  }
  class BaseEstimator {
    feature_names_in_ : NoneType
    n_features_in_
    get_params(deep)
    set_params()
  }
  class MultiOutputMixin {
  }
  class RegressorMixin {
    score(X, y, sample_weight)
  }
  class LinearModel {
    coef_
    intercept_ : float
    fit(X, y)
    predict(X)
  }
  class ElasticNet {
    alpha : float
    coef_ : list
    copy_X : bool
    dual_gap_
    fit_intercept : bool
    l1_ratio : float
    max_iter : int
    n_iter_ : list
    normalize : str
    path : staticmethod
    positive : bool
    precompute : bool
    random_state : NoneType
    selection : str
    sparse_coef_
    tol : float
    warm_start : bool
    fit(X, y, sample_weight, check_input)
  }
  class Lasso {
    alpha
    path : staticmethod
  }
  LinearModel --|> BaseEstimator
  ElasticNet --|> MultiOutputMixin
  ElasticNet --|> RegressorMixin
  ElasticNet --|> LinearModel
  Lasso --|> ElasticNet
  ndarray --* ElasticNet : coef_
  ndarray --* ElasticNet : dual_gap_
```
