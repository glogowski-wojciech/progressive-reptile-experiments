# Two gradients verification

Tags:
- `one_gradient`
- `two_gradients`


Goal of this experiment is to verify whether two optimizers, one per each column produce the same results as one optimizer for both columns. It may find errors like not applying gradient to some variable or applying it twice.

Test Accuracy for Setting | o15 | o15t | m15 | m15t
--- | --- | --- | --- | ---
One gradient | 0.96282 | 0.98272 | 0.46744 | 0.48988
Two gradients | 0.96084 | 0.98326 | 0.46316 | 0.50314
