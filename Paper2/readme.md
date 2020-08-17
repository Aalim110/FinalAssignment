# Improved Automatic Summarization of Subroutines via Attention to File Context

# Confrence:
## MSR 2020 Technical Paper

[Confrence Link](https://2020.msrconf.org/program/program-msr-2020
)

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
***

# Neural Encoder-Decoder Architecture:
It is a key supporting for all data driven code summarization techniques. It is designed for Neural Machine Translation(NMT) The origin of the architecture is **_Bahdanau et al_**.While the encoder-decoder design existed.This paper introduced attention and launched several new threats research. Since that time the number of papers using the attentional encoder-decoder design far exceeds what can be listed in one paper,with thousands of papers discussing over all improvements as well as adjustments for specific domains. Enough details are provided in next section here only briefly described over view of encoder-decoder. Encoder is provide input data representing source sentence or document on other hand decoder provides sample for that given input. After sufficient training provided to encoder and decoder the model can often generate a reasonable output from decoder given input to an encoder. Basic cocnept is that encoder and decoder are basic neural networks.the encoder RNN’s output state is given as the initial state of the decoder.During training,the decoder learns to predict outputs one word at a time based on the encoder RNN’s output state. Advancement of enocoder-decoder model focus on encoder because what encoder takes as input will be given output by decoder.The encoder-decoder design has found uses in a very wide variety of applications beyond its origin for translation. One RNN encodes a sequence of symbols into a fixed-length vector representation, and the other decodes the representation into another sequence of symbols. The encoder and decoder of the proposed model are jointly trained to maximize the conditional probability of a target sequence given a source sequence. The performance of a statistical machine translation system is empirically found to improve by using the conditional probabilities of phrase pairs computed by the RNN Encoder-Decoder as an additional feature in the existing log-linear model. Qualitatively, we show that the proposed model learns a semantically and syntactically meaningful representation of linguistic phrases.

# Our Model:
In this section,we present our prediction model. Using file context as an improvement for neural code summarization.Therefore we keep our model design simple to reduce experimental variables,while retaining the most important design features from related work.

# Overview:
The model depends on encoder-decoder architecture ,we have a source code/text input as well as an AST input to the encoder,plus summary input to the decoder we introduce a new input called“filecontext”,which is the code/text frome very other function in the same file. In this sub section,we discuss an over view visualized below:

The encoder has three types of input code/text and AST. while file context and decoder has one type input of function. .During training,a sample summary is provided to the decoder.During inference,the decoder receives the predicted summary so far,while the output prediction is the predicted next word in the summary.
Code/Text We model code/text using a word embedding space and are current network(area2).This is the same design that has been successful in several related papers.The code/text is merely the sequence of tokens from the source code for the function.
As AST discussed above three ways of AST hu et al LeClair et al Alon et al these are the models of AST. We built our modelsothatanyoneofthesemaybeused,andprovideimplementationsforeach.Later,our experiment will evaluate the effects of combining file context with each. Firstly we describe flatetting techniques of LeClair,Second,for the AST encoder by paths we will be allowed to use 100 paths which is allowed by Alon at al.
File Context This input leads to the key novelty of our model. The input itself is, essentially, the code/text data for every other function in the same file as the function we are trying to summarize. The format of this input is an nxm matrix in which n is the number of other functions in the file and m is the number of tokens in the function (technically,we pador truncate functions at m tokens so all inputs equences are the same length,and select only the first n functions from each file if more then n are available).We model the input first by using at rainable word embedding space. Note that we share this embedding space with the code/text data – there is not a separate vector space for words in the code/text input and words in the functions in the file context. Note that this necessitates the use of the same vocabulary for both inputs, which has the effect of introducing more out-of-vocab words for the code/text input(since vocabulary is calculated as the x-most common words,and the file context distorts the word occurrence count in favor of words that occur in the file context).Yet in pilot studies we found an improvement of over 20% in BLEU score when sharing this space opposed to learning different embedding spaces, not to mention reduced model size and time to train.For reference, we use dacode/text vocab size of 75k,and about 15% of this was displaced when recomputing the vocabulary with file context. Next,we use one RNN per function in the file context. This is similar to how function code/text is modeled except that for file context we only use the final state of the RNN. For function code/text (area 2), we output the RNN state for every position in the code/text sequence – that way, we can compute attention for every position in the decoder to every position in the code/text sequence(as described for NMT by Bahdanauet al.and implemented in a majority of code summarization papers). In contrast,for file context,we build a two dimensional matrix in which every column is a vector representing a function in the file context(the vector is the final state of the RNN for that function). As mentioned,we calculate attention for each encoder input to the decoder (“summary”) input. For code/text and AST sequences,we compute attention as mentioned in the previous paragraph.However,for file context,we compute attention from each positioninthesummarytoeachfunctioninthefile.Ametaphor to NMT is that the attention mechanism was origin ally designed for building a dictionary between words in one language towords in another language, by learning to emphasize the positions in the encoder  . s sentially what this does is train the model to output a word in onelanguagee.g.Hundwhenitseese.g.dogintheinput.Applied to our model for file context,the model learns to output words in code summaries when it sees functions relevant to those words. So for instance,if a function in the file context involves playing mp3 files,the model will be more likely to output words related to mp3s, music,audio,etc. In our 
revaluation (seeRQ2),we explore evidence of how our model actually does behave as we envision. To create an output prediction, we concatenate the attentionadjusted matrices from all three encoder inputs and the decoder.

# Training Procedure:
The training procedure is teacher forcing procedure means predicting summaires word at a time and prediciting models. ,we train the model by providing the three encoder inputs,plus the decoder summary input one word at a time.

[ encoder inputs ] => play mp3 files would become during training four separate samples: 
[ encoder inputs ] => <st> + ( play )
[ encoder inputs ] => <st> play + ( mp3 ) 
[ encoder inputs ] => <st> play mp3 + ( files ) 
[ encoder inputs ] => <st> play mp3 files + ( <et> ) 

Where st and et are start and end sentece tokens for readabilty we donot show padding. In training encoder will take encoder inputs and decoder sequence so far.

# Corpus Preparation:
It is provided by LeClair et al for code summarization datasets.This corpus includes around 2m Java methods paired with summaries, already cleaned and split into training/validation/test sets according to a variety of recommendations. .That paper evaluated four different splits and determined minimal variations in reported results after cleaning. For maximum reproducibility,we use“split set1” from that paper.We donot use datasets from other papers because we could not verify that they followed the dataset recommendations such as removing auto-generated code.
Corpus Preparation not include file/contetxt is it include raw material data used by LeClair at al in n x m matrices form. Note that each file context matrix didnot include the function itself – only the other methods in the file. We included these methods even if they didnot have summaries of their own.We filtered all comments and summaries from the file context so that it only included words from the code itself. It felt easy for training but in model very similar or even identical summary during training, and we decided to avoid the possibility of introducing this bias. The size of n and m is important hypermeter n controls the number of functions per file while m controls number of tokens per function .Ideally both numbers would be very high, but hardware and software limitations require us to cap them.  n and m must be in reasonable balance after testing we noted that n =20 and m = 25 is a reasonable balance. The model appears to use the function signatures and first few tokens,but later parts of the function donot appear to be useful in the filecontext, at least with the type of RNNs we used in our implementation.

# Expriments Design:
This section is all about the expriment on research questions.

# Research Questions:

Our research objective is to evaluate whether the our proposed mechanism for including file context in code summarization improves strong,recent baselines.In particular,we aim to establish whether any improvement can be at tributed to the filecon text,so we aim to reduce the number and effect of other factors.We ask the following Research Questions(RQs): 

RQ1 What is the performance of our proposed approach compared to recent baselines in terms of quantitative metrics in a standardized dataset? 
RQ2 To what extent can differences in performance beat tributed to the inclusion of file context?

The rationale for RQ1 is straight forward: to compare our approach to existing approaches. The scope of this question is to compare our work to relevant data-driven technologies,as opposed to heuristic-based/template solutions.Generally speaking,it would not be a“fair”comparison for heuristic-based techniques because a heuristic could produce a valid summary that would not be anything like there ference solution.The way to evaluate a heuristic approach is with a humans tudy,but the scale of the dataset(e.g. over 90k samples in the test set)is much too large.Therefore we follow precedent set in both the SE and NL Presearch areas,and use quantitative metrics to evaluate performance in broad terms overthe whole test set. However, there are many factors that can affect performance between one data-driven approach and another.For example,the choice of exactly which type of recurrent unit to use(e.g.LSTMvs GRU,oruni-directionalvsbi-directional)or the number of units in a hidden layer.We control as many of these factors as possible by configuring the approaches in as similar away as reasonable but there is always a question as to whether a proposed variable is actually the dominant one. Therefore, we ask RQ2 to study how file context contributed to predictions in the model.

# Methodology:
we follow the methodoly of source code summarization to predict the basline of source code that code summrization should be pridected by input through encoder and output through decoder.
We answer RQ2 in three stages.First,we provide an overview comparison of predictions by different models to determine whether the inputs (code/text, AST, file context) give orthogonal results and estimate the proportion of predictions may be helped by file context.Second,we extract specific examples to illustrate how the approach works in practice. Whenever possible, we support our claims with quantitative evidence,to minimize  the potential of bias. One key piece of evidence in the examples is from the attention layer to file context (area 6 in the overview figure, The attention layer shows which of the functions in the file context are contributing the most to the prediction. By showing that a prediction is improved when when a particular function is attended,we can demonstrate that the file context is the most likely explanation for the improvement.Finally,we explore evidence that it is prevalent for file context to improve predictions in a similar way as the example,and per formanablation study in which we train and test the model using only AST and file context.

# Expriments Result:
We present our exprimental findings and answer our research questions in this section.

# RQ1:Quantitative Measures:
Question one is all about key terms of quantative measures of whole set. adding our file context encoder increased performance in nearly all cases. .One possible explanation for the greater increase for attendgru and ast-attendgru is that the path-andgraph-based AST encoder models have many millions more parameters than the flattened AST approach(not to mention, when there is no AST encoder),and the model may have difficulty retaining some of the details in these larger encoders in the“squash” layer of the model (area 7 of overview figure in Section 4.1 and paragraph 13 of Section4.4).Recall that an over riding objective in our experimental setup is to reduce variables to create an“apples to apples”comparison.For that reason,we used fully-connected networks of 256 dimensions for all approaches in the squash layer. The result could be that the model is able to learn more details about the flattened AST encoder in the squash layer simply because of there are many fewer parameters in that encoder,while we are in effect asking the model to remember much more information in that layer in the path-andgraph-based encoders.Our recommendation for future work is to designate the size of the squash layer as a hyperparameter for tuning,perhaps with larger settings for larger encoders.We donot recommend concluding from this experiment alone that a flat AST encoder is the best design.Instead,we confine our selves to the conclusion that adding our file context encoder to the baselines improves the performance of those baselines. 

# RQ2 Effect of File Context:
Effects are being explore in three ways first is a bird eye view of results second present specific examples demonstrating how the model works. Third we provide that examples are representative of models. With BLEU we perform these kinds of examples and predictions. File context has great effect on source code summarization all is discussed above.

# Discussion/Conclusion:
The paper was all about that how file context can be used to improve neural code summarization.  Yet the question is how to make use of those clues in practice. In a nutshell, our approach is to encode in a recurrent network every subroutine in the same file as the sub routine we are trying to summarize.The result is that the model is able to use more words from that context, as in the following examples(for maximum reproducibility,number is method ID in the dataset followed by the reference summary.

As with all papers,our work carries threats to validity and limitations. For one, we use a quantitative evaluation methodology, which while in line with almost all related work and which enables us to evaluate the approach over tens of thousands of subroutines, may missnuances that a qualitative human evaluation would catch. However,space limitations prevent us from including a thorough discussion of both in a single paper, so we defer a human evaluation for extended work. Another limitation is that we evaluate only against a Javadataset. That is all about the paper.






