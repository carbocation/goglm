__goglm__ supports estimation of generalized linear models in Go.

A basic usage example is as follows:

```
glm := NewGLM(NewFamily("binomial"), data)
result := glm.Fit()
print(result.Summary())
```

`NewFamily` returns a GLM family (e.g. `Binomial`), and `data` is a
"DataProvider" as defined in the
[statmodel/dataprovider](http://github.com/kshedden/statmodel)
package.  The DataProvider is used to feed data to the GLM in chunks
using a column-oriented storage layout.  A more extensive illustration
can be found in the "examples" directory.


Supported features
------------------

* Estimation via IRLS and [gonum](http://github.com/gonum) optimizers

* Most of the more popular families, links and variance functions

* Estimation for weighted datasets

* Models can be specified using formulas

* Regularized (ridge/LASSO) estimation

* Offsets

* Unit tests covering all families with their default links and
  variance functions, and some of the more common non-canonical links


Missing features
----------------

* Performance assessments

* Model diagnostics

* Less-common GLM families (e.g. Tweedie)

* Marginalization

* Missing data handling

* Multicore optimization

* GEE

* Inference for survey data
