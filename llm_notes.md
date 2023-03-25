# LLM Notes

Acknowledgement to https://stanford-cs324.github.io/winter2022/

The classic definition of a language model (LM) is a probability distribution over sequences of tokens.
Suppose we have a vocabulary $\mathcal{V}$ of a set of tokens.
A language model $p$ assigns each sequence of tokens $x_1,\dots,x_L\in\mathcal{V}$ a probability (a number between 0 and 1):
$$
p(x_1,\dots,x_L).
$$

We can also generate a sequence given a language model.
The purest way to do this is to sample a sequence $x_{1:L}$ from the language model $p$ denoted by
$$
x_{1:L}~p.
$$
A common way to write the joint distribution $p(x_{1:L})$ is using the chain rule of probability:
$$
p(x_{1:L}) = p(x_1) p(x_2 \mid x_1) p(x_3 \mid x_1, x_2) \cdots p(x_L \mid x_{1:L-1}) = \prod_{i=1}^L p(x_i \mid x_{1:i-1}).
$$
Any joint probability distribution can be written this way mathematically, but an autoregressive language model is one where each conditional distribution $p(x_i \mid x_{1:i-1})$ can be computed efficiently (e.g., using a feedforward neural network).

In an $n$-gram model, the prediction of a token $x_i$ only depends on the last $n−1$ characters $x_{i−(n−1):i−1}$ rather than the full history:
$$
p(x_i \mid x_{1:i-1}) = p(x_i \mid x_{i-(n-1):i-1}).
$$