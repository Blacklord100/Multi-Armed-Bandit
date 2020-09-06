# Multi-Armed-Bandit

This project is co-authored with Hugo Mallet. 

We conducted our analysis over the following article: "A framework for Multi-A(rmed)/B(andit) testing with online FDR control". In short, it summarizes how to optimize the use of p-values to reject or not ""discoveries" done through A/B testing.

During this analysis, Multi-Armed-Bandits algorithms caught our interest, and we wanted to implement one for educational purposes.

In order to give this implementation a practical point of view, let's define a use-case:

- __Compagny A sells cars__ to customers through their online website
- Compagny A knows by experience the __user interface of the website infers on the customers buying behavior__
- Compagny A defined a metric: __Click-to-buy ratio__ and wants to __maximize it__
- __Compagny A has designed 4 websites to test__

The __traditional testing would be A/B testing__. For a fixed period of time (fixed according to the p-value signifiance), each website channel gets randomly attributed customers. Here, compagny A will be focusing on the Click-to-buy statistics and find the best channel for the sells. Afterward, compagny A will be releasing the best website channel to all of its customers. A/B testing is therefore pure exploration

However, this is not an optimal solution as A/B testing requires a fixed period time:

- Compagny A during the time of the testing won't be able to maximize it gains
- Customer trends might change before, during, and after the experiment making it unsuccesfull.
Therefore, one should seek for an exploration-exploitation solution, a solution that exploit the result of its exploitation while testing.

__Multi-armed-bandit (MAB) testing has no fixed period of time, nor fixed size customer random attribution.__ This algorithm will __start optimizing__ the Click-to-buy ratio from the __very start__. We will be defining a basic form of this algorithm with Thompson sampling (which is reconned to be working really well) through this material.
