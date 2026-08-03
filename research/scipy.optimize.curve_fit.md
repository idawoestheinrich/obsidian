
fit function used scipy.optimize.curve_fit:
Use non-linear least squares to fit a function, f, to data.

Optimal values for the parameters so that the sum of the squared residuals of $f(x, *popt) - y$ is minimized.

Assumes `ydata = f(xdata, *params) + eps`

The estimated approximate covariance of popt. The diagonals provide the variance of the parameter estimate. To compute one standard deviation errors on the parameters, use perr = np.sqrt(np.diag(pcov)). Note that the relationship between cov and parameter error estimates is derived based on a linear approximation to the model function around the optimum [1]. When this approximation becomes inaccurate, cov may not provide an accurate measure of uncertainty.
If the Jacobian matrix at the solution doesn’t have a full rank, then ‘lm’ method returns a matrix filled with np.inf, on the other hand ‘trf’ and ‘dogbox’ methods use Moore-Penrose pseudoinverse to compute the covariance matrix. Covariance matrices with large condition numbers (e.g. computed with numpy.linalg.cond) may indicate that results are unreliable.

With `method='lm'`, the algorithm uses the Levenberg-Marquardt algorithm through [`leastsq`](https://docs.scipy.org/doc/scipy/reference/generated/scipy.optimize.leastsq.html#scipy.optimize.leastsq "scipy.optimize.leastsq"). Note that this algorithm can only deal with unconstrained problems.