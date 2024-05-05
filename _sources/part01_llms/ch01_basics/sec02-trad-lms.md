# "Traditional" Language Models and Tasks

Let me outrageously define Traditional LMs as *any language models before the LLMs*. 

In the pre-LLM era, language models had specific & specialized architectures, datasets, and tasks. 

## Data

For example, let's look into the [sentiment analysis task](https://paperswithcode.com/task/sentiment-analysis).

> Sentiment Analysis is the task of classifying the polarity of a given text. For instance, a text-based tweet can be categorized into either "positive", "negative", or "neutral". Given the text and accompanying labels, a model can be trained to predict the correct sentiment.

How big are the datasets?

- IMDb Movie Review (2011): 50,000 movie reviews, labeled as "positive" or "negative"
- ReDial (2018): 10,000 conversation

How about [named entity recognition](https://paperswithcode.com/datasets?task=named-entity-recognition-ner)?

- CoNLL (2003): 22,137 sentences
- Few-NERD (2021): 118,200 sentences

It's all relatively, but these are very small (and specific) compared to the training data for LLMs.

## Models

For classification, a deep learning models with a classification head used to have under or above a million parameters. Or - 0.001B parameters. 

Models for named entity recognition were not too different.

An exception is machine translation, where things were - could be, and had to be - much larger. Until very recently though (before 2020), the models were still definitely under 1B.

More importantly, before LLMs (also before BERTs; which will be covered in the next section,) all the models were specialized for a specific task. 
This means everything is scattered; models, datasets, etc.. You have one model for one task. You need many models for many tasks. 
And that was just natural, as they should be.
