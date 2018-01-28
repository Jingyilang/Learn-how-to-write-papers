## Abstract
DNNs 是很有力的模型，在困难的学习任务上取得了优越的效果。 尽管只要大规模有标注训练集是可得的，DNNs就会工作的很好，
但是它们不能被用来map sequence to sequence。 本文中，我们提出一个通用的适用于sequence 学习的端到端方法，对序列
结构作出细小假设。 我们的方法是用一个多层的LSTM to map input sequence to a 固定维数的 vector, 然后用另外的深度LSTM
来从这一vector中解码出target sequence.

Deep neural networks are powerful models that achieved excellent performances on difficult learning tasks. 
Although DNNs work well whenever large labeled train sets are available, they cannot be used to map sequence
to sequence. In this paper, we present a general end-to-end approach to sequence learning that makes minimal 
assumption on the sequence structure. Our method uses a multilayered LSTM to mao input sequence to a vector of
fixed dimensionality, and then another LSTM decode to target sequence form the vector. 

## 1 Introduction

DNNs 是相当有力的机器学习模型，在很多困难的问题上 比如语音识别，取得了优越的效果。 DNNs之所以是有力的是因为它们 可以以
适当数量的步骤执行任意的并行计算。一个DNNS有力性惊奇例子是它们。。。。 所以，虽然神经网络与传统的统计模型有关，它们却
学习更复杂的计算。更重要的是，大型DNNS可以用监督反向传播在训练只要有标注的训练集有足够的信息to specify 网络参数。因此，
如果存在取得了良好结果的DNN的一组参数集， 监督反向传播会发现这些参数并解决这个问题。

DNNs are extremely powerful models that achieved excellent performances on difficult problems such as speech
recognition. DNNs are powerful because they can perform arbitraay parallel compution for a modest number of steps
. A surprise expample of the power fo DNNs is ... . While neural nerworks are relevant to conventional statist-
ical models, they learn an intricate computation. Furthermore, large DNNs can be trained withe supervised back-
propagation whenever the labeld training set has enough infor to specify the networks parameters. Thus, if there
exists a parameter setting of DNNs that achieves good results, supervised backpropagation will find these parameters
and solve the problem.

如果除去它们的灵活性和有力性不说，DNNs 仅仅能用在哪些输入和输出能被编码成固定vector的问题上。 这是一个很大的局
限， 因此很多重要的问题
