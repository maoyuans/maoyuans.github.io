---
layout: default
title: Research
nav_exclude: true
search_exclude: true
---

<script
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"
  type="text/javascript">
</script>

# Research Interests

A great majority of my experience studying computer science has been intertwined with machine learning and artificial intelligence. Despite having taken both theoretical and practical introductory courses to machine learning as an undergraduate student, I did not find myself ever drawn to the idea - ever satisfied with the advantages and the guarantees.

It is only many years later that I fully understood the reason behind this feeling. The motivation is two-fold - one philosophical and not relating to this perspective; the other that machine learning is fundamentally probabilistic - it is hard to obtain rigorous, deterministic theoretical guarantees for models and classifiers, and is often prone to outliers in the input data via overfitting, underfitting, et cetera.

How can we solve these problems - or help alleviate them, from a perspective from without the machine learning field? Most of my research projects and interests revolve around the overarching idea of using classical algorithms to augment and facilitate machine learning algorithms, and improve the stability and robustness of machine learning methods. I like to summarize it broadly as "Algorithms ***for*** machine learning".

## Learning-Augmented Algorithms

Many problems in the classical algorithms setting exhibits impossibility results - most prominently in online settings, where algorithms have to make irrevocable decisions without knowing future inputs. On the other hand, while machine learning models excel at predicting the future based on observed, historical data and are efficient in practice, it is prone to outliers and can perform arbitrarily badly in extreme cases. 

These worst-case scenarios make machine learning methods impractical to deploy in certain *safety-critical* scenarios, such as infrastrcuture management and energy scheduling. A natural question is: How can we combine the efficiency of machine learning and the stability of classical algorithms, to obtain the best of both worlds?

The study of *learning-augmented algorithms* aims to answer by using *untrusted predictions* generated by machine learning methods to augment classical algorithms, to possibly improve their performance and break impossibility results if these predictions are accurate, but also maintain comparable performance to classical, non-learning-augmented state-of-the-art algorithms even if the advice is arbitrarily erroneous. Crucially, we make no assumption on these predictions - it is important to use them in our algorithms prudently.

My previous projects in learning-augmented algorithms involve general-purpose settings, such as online covering and packing linear programs, semidefinite programs, and programs with convex or concave objectives. These settings lead to unifying frameworks that can be applied to a large variety of problems in online optimization. Tightly analyzing these algorithms is however difficult, due to a lack of problem structure to rely on.

This line of work also led to the (re-)discovery of simple, possibly folklore, learning-augmented algorithms based on the idea of switching between the prediction and the solution of any state-of-the-art online algorithm as a black-box procedure. These algorithms are surprisingly simple compared to their sophisticated counterparts based on primal-dual methods, but can achieve near-optimal performances. Such ideas are classical for online optimization, but is much less prevalent in the learning-augmented field.

What structural properties of the problems we studied allows these simple, switching-based algorithms to be optimal? For which problems and settings can we obtain these simple algorithms, that uses classical online algorithms as a black-box to obtain optimal algorithms? These are meta-level conceptual questions that may be important to our understanding of the fundamental power of external predictions, and I am very interested in exploring these questions.

## Optimality in Statistical Estimation, Beyond the Worst-Case

Learning properties of unknown distributions from observing random samples is a fundamental primitive of statistics: In particular estimating the mean of an unknown distribution in one-dimension. It has been long known that the sample mean is optimal when the unknown distribution is Gaussian, but it is prone to outliers in the sample set, and can perform exponentially worse on general distributions. A long line of research has culminated in optimal mean estimators achieving the *sub-Gaussian rate*, performing as well as the sample mean on Gaussian distributions on *any* distribution, even up to the constants.

These results, however, are only optimal *in the worst-case*: any estimator cannot perform better than sample mean on Gaussian distributions. **Can we beat the sub-Gaussian rate, at least for some easier distributions?** Can we develop "instance-by-instance" algorithmic and analysis techniques? Is it possible for estimators to leverage beneficial features of their input distribution to beat the sub-Gaussian rate, without explicit knowledge of these features?

My prior work resolves this question with an unexpectedly nuanced answer: Yes, in certain regimes, such as finite-sample, or symmetrical assumptions; But in general, no. In an appropriate sense of "hardness", every distribution is at least as "hard" as Gaussian distributions. We rigorously define the hardness of an instance and the accompanying "neighborhood optimality", which to our knowledge is the first notion of optimality for mean estimation *beyond the worst-case*. 

Under our new definition, we showed that the classical median-of-means estimator, as well as the state-of-the-art Lee-Valiant estimator, are both optimal beyond the worst-case. In particular, we establish a connection between robustness against adversarially corrupted data and instance-by-instance optimality, and show that any adversarially robust mean estimator is also neighborhood optimal. 

While this line of work is conceptual and definitional, it is very intriguing to me that the optimality of certain classical algorithms can extend beyond the worst-case. How can we better explore the landscape of optimality in an instance-by-instance fashion, for other statistical estimation problems, and beyond the field of statistics? I am interested in investigating and answering these questions in the future.