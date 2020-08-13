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
Neural machine translation models are used to automatically generate a document from given source code since this can be regarded as a machine translation task. Source code summarization is one of the components for automatic document generation, which generates a summary in natural language from given source code. This suggests that techniques used in neural machine translation, such as Long Short-Term Memory (LSTM), can be used for source code summarization. However, there is a considerable difference between source code and natural language: Source code is essentially {\em structured}, having loops and conditional branching, etc. Therefore, there is some obstacle to apply known machine translation models to source code.
Software documentation best aspect is subroutines description in the source code.Programmers navigate subroutines to understand source code. These descriptions are backbones of software documantation.how to use them even a microphone for web confrence say alot to programmers that what subroutine does.Researches are trying to make automatic summarization to reality. Early researches are amnually encoding of human knowledge such as sentence templates till AI based approaches were introduced. AI based summaries is inspired by (NMT)Neural Machine Translation from the natural language processing research area Typically NMT problems using pairs of sentences in one language and translate them in other language. The existing approaches have been promising but not yet excellent performance. Encoder and decoder neural architecture have been focused. The progammers use these techinques to summarize subroutines. In this paper automatic summarization of subroutines hass been enhanced by using the file context of the subroutines combined with the subroutines’code. some approaches of subroutine summarization had been proposed mentioned below.
1).  model the signatures of all other subroutines in the same file also using recurrent nets
2).Use an attention mechanism to learn association between subroutines in the file context to words in the target subroutine’s summary during training.

# 2.  PROBLEM,SIGNIFICANCE,SCOPE:
The problem target is that source code summarization.means documented description of code with the help of natural language.They focused on writing subroutine summary because it has high impact on sofware documenatation. Subroutines summary are analogus to Machine Translation(MT) because there is large potential for cross pollination ideas with natural language. processing research area, as a number of new interdisciplinary workshops and NSF-funded meetings have highlighted. This cross pollination encourged us by maximizing our work.
Yet despite crossover with NLP,this work is firmly in the field of Software Engineering. we can say a brief history of code summarization is focused on research of mannual writting.when Neural Machine Translation was applied to source code and comments.The first NMT applications treated code summarization as essentially an MT problem.source code was the“source”language while summary comments were the“target”,compared to an MT setting when e.g.French sentences were a source and equivalente.g.English sentences the target. Therefore, there is some obstacle to apply known machine translation models to source code.
Abstract syntax trees (ASTs) capture these structural properties and play an important role in recent machine learning studies on source code. Tree-LSTM is proposed as a generalization of LSTMs for tree-structured data. However, there is a critical issue when applying it to ASTs: It cannot handle a tree that contains nodes having an arbitrary number of children and their order simultaneously, which ASTs generally have such nodes. To address this issue, we propose an extension of Tree-LSTM, which we call \emph{Multi-way Tree-LSTM} and apply it for source code summarization. As a result of computational experiments, our proposal achieved better results when compared with several state-of-the-art techniques. The paper will further move to file context to improve source code.A scholarship objective of this paper is to accelerate the community’s progress by demystifying key aspects of using neural networks for code summarization.

# Background and Related Work:
This section discussion key background items including related work from software engineering and natural language processing.

# Source Code Summarization:
As already mentioned that source code summarization has great literature in the field of software engneering. herustic method based source code giving a way to recent data driven.there are five very closely related data-driven papers on source code summarization which we cover in detail.
>The first of the five closely-related papers is by **Iyer et al**.This is a earlier work used neual encoder decoder for summarization..The work set the foundation for significant advancements,but in retrospect was a fairly straightforward application of off-the-shelf NMT technology. c# code were used as input and summary descriptions as output.Many changes were made to input by preprocessing in an attemp to maximize performance by focusing on the important parts of code. Later on big data herustic were used to select some important points from code preprocessing. then fed to an encoder-decoder system that, in it’s overall structure, remained unchanged from NMT approaches for natural languages.

>**Hu et al** in 2018 improved it and stated that abstract tree more effective. Their ideas should give us more detail about code behaviour as compare to words in code alone.Improved pre directions of code summary. vast majority of encoder-decoder is ecounterd as problem while the AST tree solution is structural based Traversal(SBT).  which is essentially analgorithm for flattening the AST into a sequence and using the components of the AST to annotate words from the code.

>Next, **LeClair et al** observed form Hu et al that there is two different blended information structure from AST and identifier names etc. Image captioning were introduced it will give us great rsults when two different types are processed seprately.differnt architecures were designed for the word sequence and SBT/AST.sequences in separate recurrent nets with separate attention mechanisms,and concatenates the results into a context vector just prior to prediction.

>While **Wan et al** reports improvement with hybrid AST + code attention approach.  They also show how to use reinforcement learning to improve performance by several percent. While we do not dispute that the RL-based approach helps, we donot use it this paper because our goal is to show how file context adds orthogonal information to AST+code approaches. The RL-based approach is more like an improved training procedure,as opposed to adding new information to the model.Ultimately,we used LeClair et al's approach as a baseline because it is simpler (to reduce experimental variables) ands lightly more recent.

>At around the same time, **Alon et al** and **Allamanis et al**,They noted that is AST is best to source code summary. It is a useful addition for prediction that force system to learn tree model structure sequence. Yet these papers diverge substantially on the solution. Alonet al.extract a series of paths in the AST and treat each path as a different sequence, while Allamanis et al.  propose using a graph-based neural net work to model the source code.The first approaches to use structural information flattened the AST into a sequence. Recently, more complex approaches based on random AST paths or graph neural networks have improved on the models using flattened ASTs. However, the literature still does not describe the using a graph neural network together with source code sequence as separate inputs to a model. Therefore, in this paper, we present an approach that uses a graph-based neural architecture that better matches the default structure of the AST to generate these summaries. We evaluate our technique using a data set of 2.1 million Java method-comment pairs and show improvement over four baseline techniques, two from the software engineering literature, and two from machine learning literature.

