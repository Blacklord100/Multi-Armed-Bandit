# Multi-Armed-Bandit

This project is co-authored with Hugo Mallet. 

We conducted our analysis over the following article: "A framework for Multi-A(rmed)/B(andit) testing with online FDR control". In short, it summarizes how to optimize the use of p-values to reject or not ""discoveries" done through A/B testing.

During this analysis, Multi-Armed-Bandits algorithms caught our interest, and we wanted to implement one for educational purposes.

In order to give this implementation a practical point of view, let's define a use-case:

- Compagny A sells cars to customers through their online website.
- Compagny A knows by experience the user interface of the website infers on the customers buying behavior
- Compagny A defined a metric: Click-to-buy ratio and wants to maximize it
- Compagny A has designed 4 websites to test.

The traditional testing would be A/B testing. For a fixed period of time (fixed according to the p-value signifiance), each website channel gets randomly attributed customers. Here, compagny A will be focusing on the Click-to-buy statistics and find the best channel for the sells. Afterward, compagny A will be releasing the best website channel to all of its customers. A/B testing is therefore pure exploration

However, this is not an optimal solution as A/B testing requires a fixed period time:

- Compagny A during the time of the testing won't be able to maximize it gains
- Customer trends might change before, during, and after the experiment making it unsuccesfull.
Therefore, one should seek for an exploration-exploitation solution, a solution that exploit the result of its exploitation while testing.

Multi-armed-bandit (MAB) testing has no fixed period of time, nor fixed size customer random attribution. This algorithm will start optimizing the Click-to-buy ratio from the very start. We will be defining a basic form of this algorithm with Thompson sampling (which is reconned to be working really well) through this material.
