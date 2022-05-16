<details>
  <summary>How to generate UML file from sklearn or any other project?</summary>
  
  <br>
  
  Clone the `scikit-learn` repo and from main dir run:
  
  ```
  $ pyreverse -o mmd -s1 -c sklearn.linear_model._coordinate_descent.Lasso sklearn/linear_model
  ```
  
  ```
  $ pyreverse -o png -s1 -c sklearn.linear_model._base.LinearRegression sklearn/linear_model
  ```
  
  More info at: https://github.com/PyCQA/pylint/issues/6571

</details>
