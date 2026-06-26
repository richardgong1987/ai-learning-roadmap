# Lesson 26: Bayes Theorem

## Status

Completed.

## Core idea

Bayes Theorem is a rule for updating belief when new evidence appears.

It answers this question:

Given that we observed some evidence, how likely is the original cause or hypothesis?

## Concrete intuition

Imagine a medical test.

- A disease is rare.
- The test is usually accurate.
- A person tests positive.

Bayes Theorem helps answer:

How likely is it that the person really has the disease?

The important lesson is that a positive test result does not depend only on test accuracy. It also depends on how common the disease was before testing.

## Main formula

\[
P(A \mid B) = \frac{P(B \mid A)P(A)}{P(B)}
\]

Meaning:

- \(A\): hypothesis or cause
- \(B\): observed evidence
- \(P(A)\): prior probability, the belief before seeing evidence
- \(P(B \mid A)\): likelihood, the probability of seeing evidence B if A is true
- \(P(B)\): evidence probability, the overall probability of seeing B
- \(P(A \mid B)\): posterior probability, the updated belief after seeing evidence

## Step-by-step numerical example

Suppose:

- 1% of people have a disease.
- If someone has the disease, the test is positive 99% of the time.
- If someone does not have the disease, the test is still falsely positive 5% of the time.

For 10,000 people:

- Diseased people: 100
- Non-diseased people: 9,900
- True positives: 99% of 100 = 99
- False positives: 5% of 9,900 = 495
- Total positive tests: 99 + 495 = 594

So if a person tests positive:

\[
P(\text{Disease} \mid \text{Positive}) = \frac{99}{594} \approx 0.1667
\]

The probability is about 16.67%, not 99%.

## Machine learning connection

Bayes Theorem is important in machine learning because models often update predictions from evidence.

Examples:

- Spam filtering: given certain words, estimate whether an email is spam.
- Medical diagnosis: given symptoms or test results, estimate disease probability.
- Classification: given features, estimate the probability of a class.

Naive Bayes classifiers use Bayes Theorem with a simplifying independence assumption.

## Practical warning

Do not confuse \(P(A \mid B)\) with \(P(B \mid A)\).

Example:

- \(P(\text{Positive} \mid \text{Disease})\): probability the test is positive if the person has the disease.
- \(P(\text{Disease} \mid \text{Positive})\): probability the person has the disease if the test is positive.

These are different.

## Key technical terms

- Bayes Theorem: 贝叶斯定理
- Prior Probability: 先验概率
- Posterior Probability: 后验概率
- Likelihood: 似然
- Evidence: 证据
- Conditional Probability: 条件概率
- Hypothesis: 假设
- False Positive: 假阳性
- Naive Bayes: 朴素贝叶斯

## Next lesson

Lesson 27: Linear Regression.
