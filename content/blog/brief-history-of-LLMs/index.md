+++
title = "A Brief History of LLMs Part-1"
date = 2026-04-20
description = "Ever wondered how ChatGPT, Gemini, Claude and a ton of other agentic AI tools came into existence ? This post breaks down the history, architectural shifts and major milestones that shaped the AI landscape as we know it today."
[extra]
author = "R Uthaya Murthy"
author_link = "https://uthayamurthy.com"
+++

If you look at how we use AI today, from assistance in writing college assignments to coding assistants that help us build things in 24 hours that would earlier require months, it is really hard to believe how fast things have moved. These AI Systems are powered by AI Models called Large Language Models (or LLMs in short). While most of the world woke up to this wonderful tech on 30th November 2022, with the release of ChatGPT, the actual groundwork started years earlier. In this post, I will walk you through the brief history of Large Language Models, showing how we went from simple next word prediction systems to multi-agent systems of the modern era.

# RNNs to LSTMs: The Foundation of Language Modeling

Before we had the massive language models of today, the field of natural language processing relied heavily on Recurrent Neural Networks (RNNs). If you wanted a machine to understand a sentence, it had to read similar to how humans do, one word at a time, in order.

RNNs were designed with a looping mechanism that allowed them to pass information from one step to the next. This was a necessary step up from older models that treated words in isolation, but RNNs had a major flaw. They suffered from something similar to Amnesia. This short term memory loss problem was due to a technical issue known as the vanishing gradient problem. By the time the RNN reached the end of a long paragraph, it would already forget what the first sentence was about.

To fix this, researchers introduced Long Short-Term Memory networks (LSTMs). LSTMs added a system of internal gates that could regulate the flow of information, deciding which context to keep and which to throw away as it processed the text. This allowed the models to retain context over long stretches of text.

However, even with the improvements that LSTMs brought, the fundamental bottleneck still remained. Since they processed text sequentially, that is word by word, they were very slow to train. It wasn't possible to parallelize the work across multiple processors. This sequential nature meant there was a hard limit on how much data these models could learn from and how large they could scale. The field of NLP was stalled because of this architectural limitation and was waiting for something that could break this limitation.

![Evolution of Language Models: From RNN to LSTM to Transformer architectures](rnn_lstm_transformer_infographic.png)

# How "Attention" Revolutionized Natural Language Processing

In 2017, a team of researchers from Google published a paper titled "Attention Is All You Need". This paper introduced the Transformer architecture, which provided the exact solution needed to break the bottleneck that held back the previous language models. The Transformers completely discarded the sequential, word by word processing of RNNs and LSTMs.

![The First Page of Attention Is All You Need Paper](attention-is-all-you-need.jpg)

Instead, the Transformers allow parallel processing during training, which significantly improves efficiency compared to sequential models like RNNs. Basically, it paid attention to longer sequences of text (say an entire sentence or paragraph) at the same time, which allowed it to capture subtle nuances from the text that would otherwise be lost if we looked at one word at a time. It accomplished this through a mechanism called "self attention". Self Attention allows the model to analyze every word in a sentence at the exact same time and determine which words are most relevant to each other, regardless of their physical distance in the text.

Let's look at an example.

> "I didn't submit the assignment because the deadline for it was far away."

Here, "it" refers to assignment.

Now:

> "I didn't submit the assignment because I was lazy."

Here, "I" refers to me of course.

RNNs struggled with this sort of things. When there was more than one noun in a sentence, they struggled to associate the right one with the right pronoun.
However, since transformers looked at the entire text at the same time, it could understand and deduce the pronoun accurately.

Another advantage that transformers had was, since they processed everything simultaneously rather than waiting for the previous words to finish, the computations could be easily parallelized across multiple processors. This architectural shift eliminated the previous limits on scaling. It allowed developers to train models much faster and on much bigger datasets, laying the groundwork for the modern AI ecosystem.

# BERT And People using LLMs for the first time

Following the Transformer breakthrough, Google introduced BERT (Bidirectional Encoder Representations from Transformers) in 2018. Before BERT, models mostly read text in a single direction, usually from left to right. BERT changed this by reading the entire sequence of words at once, in both directions. This means that it looked at the words that came before and after a specific word to fully grasp its true context. This bidirectional approach made BERT incredibly good at understanding the intent behind complex or conversational phrases.

In late 2019, Google integrated BERT into its core search engine. This was a massive milestone because Google Search could actually understand the difference between the nuances of prepositions like "to" or "for" in search queries rather than just blindly matching keywords.

Because of this Search Integration, BERT was technically the first large language model (though it is not that large compared to modern LLMs) that the masses used on a daily basis. Billions of people were suddenly interacting with an LLM everyday, even if they had no idea that they were using one !!!

# OpenAI's Early Experiments and The Birth of the GPT Series

While Google was using the Transformer architecture to look into both directions with BERT,OpenAI decided to take a different route. Instead of focusing just on understanding the text, they wanted to focus on generation. They built a model that read text strictly from left to right, with one simple goal, predicting the next word.

This led to the creation of the first Generative Pretrained Transformer or GPT-1 in 2018. The idea was to pre train the model on a massive amount of text so that it could learn the patterns of human language and then, from its understanding, could complete the given sentence.

Things really started getting interesting in 2019 with the release of GPT-2. OpenAI realized that making models bigger and training them on larger datasets could make it significantly better. This realisation has shaped how AI development takes place for the next couple of years.

Because of this scale, GPT-2 was suddenly capable of generating coherent, multi paragraph text. It could write realistic sounding (though mostly absurd by common sense) essays, stories and even news articles from a simple starting prompt. This was also around the time when I started exploring about LLMs. I remember looking at that unicorn example (a news article that said how unicorns are real) written by GPT-2 and generating a few funny text myself. OpenAI back then refused to release it to the world initially because they were worried that it would mass produce spam and fake news.

Around this same time, researchers noticed something else that was entirely unexpected. By simply scaling up this next word predictor model and feeding more data into it, the model started learning things it was never explicitly programmed to do. For instance, they realised that the model could perform basic math and even translate between languages, just by predicting what should logically come next in a sequence !!! This discovery of "emergent abilities" proved that simply scaling up could lead to surprisingly advanced capabilities.

## Continued in Part-2
