# LLM Notes

Acknowledgement to https://stanford-cs324.github.io/winter2022/

The classic definition of a language model (LM) is a probability distribution over sequences of tokens.
Suppose we have a vocabulary $\mathcal{V}$ of a set of tokens.
A language model $p$ assigns each sequence of tokens $x_1,\dots,x_L\in\mathcal{V}$ a probability (a number between 0 and 1):
$$
p(x_1,\dots,x_L).
$$

We can also generate a sequence given a language model.
