# Improved Automatic Summarization of Subroutines via Attention to File Context

# Confrence:
## MSR 2020 Technical Paper

>Venue: When
Tue 30 Jun 2020 14:48 - 15:00 at MSR:Zoom - ML4SE 
Chair(s): **_Kevin Moran_**

# Authors:

## 1. Saqib Haque

![Author Image](./image4.jpg)

## 2. Alexendar LeClair

![Author Image](./image5.jpg)

## 3. Lingfie wu

![Author Image](./image6.jpg)

 ## 4. Collin McMillan

![Author Image](./image7.jpg)

[Preprint Link](https://arxiv.org/abs/2004.04881)

[Media URL](https://youtu.be/PKner74jiso)

# Abstract:
Software documentation largely consist of short natural language to summarize subroutines.These subroutines helps programmers to understand source code summarization.This paper is all about subroutine context.

# 1. Introduction:
Software documentation best aspect is subroutines description in the source code.Programmers navigate subroutines to understand source code. These descriptions are backbones of software documantation.how to use them even a microphone for web confrence say alot to programmers that what subroutine does.Researches are trying to make automatic summarization to reality. Early researches are amnually encoding of human knowledge such as sentence templates till AI based approaches were introduced. AI based summaries is inspired by (NMT)Neural Machine Translation from the natural language processing research area Typically NMT problems using pairs of sentences in one language and translate them in other language. The existing approaches have been promising but not yet excellent performance. Encoder and decoder neural architecture have been focused. The progammers use these techinques to summarize subroutines. In this paper automatic summarization of subroutines hass been enhanced by using the file context of the subroutines combined with the subroutines’code. some approaches of subroutine summarization had been proposed mentioned below.
1).  model the signatures of all other subroutines in the same file also using recurrent nets
2).Use an attention mechanism to learn association between subroutines in the file context to words in the target subroutine’s summary during training.

# 2.  PROBLEM,SIGNIFICANCE,SCOPE:




