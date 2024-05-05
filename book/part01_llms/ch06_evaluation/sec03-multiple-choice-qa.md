# Multiple Choice QA

If vibe checks are a bit too subjective for your taste; LM Arena is to slow and expensive to run – there are more objective ways to evaluate language models too. One popular method is multiple-choice question answering (QA) evaluation.

The idea is simple: present the language model with a question and a set of multiple-choice answer options, and see if it can select the correct answer. This is typically done by having the model generate text completions for each answer option, and then selecting the option with the highest probability according to the model's own scoring.

```{admonition} Multiple Choice QA
Multiple Choice QA is to provide a set of a question and choices to a LLM as a prompt and measure if the LLM would generate the correct answer.    
```


So why is multiple-choice QA so popular for evaluation? A few reasons:

1. **Simplicity**: It's straightforward to set up and run – just need a dataset of questions and answers.
2. **Scalability**: Unlike vibe checks, you can evaluate on thousands or millions of QA examples without breaking the bank on human annotations.
3. **Objectivity**: There's a clear right or wrong answer, removing some of the subjectivity of human ratings.

Of course, multiple-choice QA evaluation has its own limitations:

1. **Too simple?**: Real-world language tasks often involve more open-ended generation, which QA doesn't capture well.
2. **No interactiveness**: It doesn't evaluate the back-and-forth conversational abilities of language models.
3. **Potential for overfitting**: Many QA datasets like MMLU are often included in the pretraining data, so models may be overfitted and scores inflated.

That last point is an important one – currently, many of the popular QA benchmarks used for evaluation are also included in the training data for large language models. This means that the QA scores you see reported may not be fully representative of the model's true capabilities on unseen data.

So while multiple-choice QA is a useful tool in the evaluation toolbox, it's just one piece of the puzzle. As with any evaluation method, it's important to understand its strengths, weaknesses, and potential biases before drawing any major conclusions.