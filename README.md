# Haskell AI (HAI)
Minimalistic implementation of a [basic neural network](https://iamtrask.github.io/2015/07/12/basic-python-network/) with [backpropagation](https://en.wikipedia.org/wiki/Backpropagation) in Haskell using only the Prelude, [Data.Matrix](https://hackage.haskell.org/package/matrix-0.3.6.1) and [System.Random](https://hackage.haskell.org/package/random).

## Run
Code runs using [Stack](https://docs.haskellstack.org/en/stable/README/) to manage imports. First clone the repository, then run

```zsh
stack build
stack exec hai-exe
```
or alternatively just,

```
stack run
```

## Code
The code can be found in [app/Main.hs](app/Main.hs) and [src/Lib.hs](src/Lib.hs). The latter includes the *train* function whereas the former has the *main* monad which initializes the matrices and calls the *train* function.
The *X* matrix in [app/Main.hs](app/Main.hs) can be changed (to experiment) and the amount of epochs in the *train* function can be changed.

## Results
```zsh
Training Data X:
┌             ┐
│ 1.0 0.0 1.0 │
│ 1.0 1.0 1.0 │
│ 0.0 0.0 1.0 │
└             ┘
Desired Ouput Y:
┌     ┐
│ 1.0 │
│ 1.0 │
│ 0.0 │
└     ┘
Result After Training:
┌                      ┐
│   0.9968757999762028 │
│   0.9993985458752835 │
│ 3.899624248201951e-3 │
└                      ┘
```
The last matrix is the final approximation of the desired output *Y* above it after 100.000 epochs of training on the *X* matrix training data. As you can see, it converged to the desired output.

## Possible Additions
- MNIST Classifier
- [Repa arrays](https://hackage.haskell.org/package/repa) and [Repa algorithms](https://hackage.haskell.org/package/repa-algorithms-3.4.1.3)
- [Good read on randomness in Haskell](https://jtobin.io/randomness-in-haskell)
- [OG Tutorial "Future Work" section](https://iamtrask.github.io/2015/07/12/basic-python-network/)
