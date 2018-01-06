ACL2016-1040
## Abstract
许多过去的中文分词方法是将该问题看做是character-based序列标注问题，所以只捕捉到了包含固定尺寸窗口的上下文信息和简单的相邻tags的相互作用。（**简要
介绍了任务，指出了过往方法的不足**）本文中，我们提出一个新颖的neural network，其中取消context window和采用complete segmentation history。我们
的模型在character上采用一个gated combination NN 来产生候选词的分布式表示，然后将其給入LSTM 语言评分模型（**介绍本文的方法及其特点**）。在benchmark 
datasets的实验表明没有现存方法那样特征工程的帮助下，我们的模型相比于最好的模型取得了具有竞争力的或更好的效果。

Many previous approaches to Chinese word segmentation formalize this problem as character-based sequence labeling task so that only context info within fixed size local windows and interactions between adjacent tags can be capture. in this pater, wo proposed a novel neural network, which elimaate context window and utilize complete segmentation history. Our model employs a gated combination NN over character to produce distributed representation of word candidates, which are then given to a LSTM language scoring model. Experiments on benchmark datasets show that without the help of featurs engineering as most existing approaches, our mdoels achieve competitive or better performances with previous state-of-the-art methods.

1 Introduction
许多东亚语言包括汉语是没有明显的word delimiters， 所以，分词的处理这些语言初步措施，自从某，许多方法将中文分词视为序列标注问题with character position tags，这就可以被监督学习方法处理，如最大熵模型和条件随机场。但是这些方法都严重依赖人工设计特征的选择（**介绍任务的由来，传统方法及其不足**）。
Most east Asia language including Chinese are written without explicit word delimiters, therefor, word segmentation is a preliminary step for processing those languages. Since , most methods formalize Chinese word segmentation as suqence labelling problem with character position tags, which can be handled with supervised learnig methods such as ME and CRF; However, those mothods heavily depend on handcrafted features.

最近，神经方法因为最小化特征工程影响的能力在NLP任务中被广泛应用。在CWS中，某采用一个某提出的通用NN结构序列标注问题。然后采用chatacter-based embedding 输入进两层的nerwork. 某通过对local context和  previous tags的相互作用进行建模而提升了上一个方法的性能。。。（**本系列以往方法**）

尽管有差异，所有的这些方法都被设计成通过一个一个地给序列中的chatacter分配labels 来解决CWS。在每一步的inference中，这些方法基于(i)context features within a fixed sized local window 和 (ii)tagging history of previous one 来计算character的tag scores.

Despite the differences, all these mothods are designed to sovle CWS by assigning labels to the characters in the sequence one by one. At each time of the inference, these mothod compute the scores the chatacter based on (i)(ii)

然而， the tag-tag 转换 不足以对对以往分割决策的复杂影响进行建模，尽管有时它是后时刻分割决策的关键线索。 The fixed context window size， 在其他方法中为特征工程二广泛采用的，同样限制建模多种距离的灵活性。 但是， the word-level info, which is the greater granularity unit as suggested in , 也没有被采用（**本系列以往方法的不足**）。

Nevertheless, the tag-tag transition is insufficient to model the complicated influence from previous segmentation decisions, through it sometimes could be a crucial clue to later segmentation decision.The context window size, which is widely used by these method for features engineeting, also restricts the flexibility of modeling diverse distance. Moreover, the word-lever info, which is the, as suggexted in ,remains unemployed.

为了减少在以往方法里的缺点和释放哪些不方便的限制比如说the fixed sized context window, 本文做出最新的尝试将CWS重新视为视为一个直接分割学习任务。我们的方法不讲单个chatacter上做tagging decision， 而是直接评估不同分割句子的相对可能性, 然后搜索得分最高的分词.



