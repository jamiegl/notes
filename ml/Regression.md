# Regression

## Linear

Very simple minimisation of $\ell_2$ norm. Coefficients that minimise are given by:

$$
\bm{\hat{\beta}} = (\textbf{X}^{\intercal}\textbf{X})^{-1}\textbf{X}^{\intercal}\textbf{y}
$$

Can be solved by via matrix decompositions such as QR or SVD.

### sklearn

`sklearn.linear_models.LinearRegression` is the class for applying linear regression to data. It has no hyperparameters exposed. Solver used depends on problem but see [LAPACK: dgelsd](https://www.netlib.org/lapack/explore-html/d7/d3b/group__double_g_esolve_ga94bd4a63a6dacf523e25ff617719f752.html) for the SVD implementation.

## Ridge
