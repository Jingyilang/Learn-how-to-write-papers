ACL2016-1040
## Abstract
许多过去的中文分词方法是将该问题看做是character-based序列标注问题，所以只捕捉到了包含固定尺寸窗口的上下文信息和简单的相邻tags的相互作用。（**简要
介绍了任务，指出了过往方法的不足**）本文中，我们提出一个新颖的neural network，其中取消context window和采用complete segmentation history。我们
的模型在character上采用一个gated combination NN 来产生候选词的分布式表示，然后将其給入LSTM 语言评分模型（**介绍本文的方法及其特点**）。在benchmark 
datasets的实验表明没有现存方法那样特征工程的帮助下，我们的模型相比于最好的模型取得了具有竞争力的或更好的效果。
Many previous approaches to Chinese word segmentation formalize this problem as character-based sequence labeling task so that only context info within fixed size local windows and interactions between adjacent tags can be capture. in this pater, wo proposed a novel neural network, which elimaate context window and utilize complete segmentation history. Our model employs a gated combination NN over character to produce distributed representation of word candidates, which are then given to a LSTM language scoring model. Experiments on benchmark datasets show that without the help of featurs engineering as most existing approaches, our mdoels achieve competitive or better performances with previous state-of-the-art methods.
1
