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
如果存在取得了良好结果的DNN的一组参数集， 监督反向传播会发现这些参数并解决这个问题。**DNN很厉害**

DNNs are extremely powerful models that achieved excellent performances on difficult problems such as speech
recognition. DNNs are powerful because they can perform arbitraay parallel compution for a modest number of steps
. A surprise expample of the power fo DNNs is ... . While neural nerworks are relevant to conventional statist-
ical models, they learn an intricate computation. Furthermore, large DNNs can be trained withe supervised back-
propagation whenever the labeld training set has enough infor to specify the networks parameters. Thus, if there
exists a parameter setting of DNNs that achieves good results, supervised backpropagation will find these parameters
and solve the problem.

如果除去它们的灵活性和有力性不说，DNNs 仅仅能用在哪些输入和输出能被编码成固定vector的问题上。 这是一个很大的局限， 
因为很多重要的问题表达成序列-预先不知道长度的最好的。比如说，语音识别和机器翻译是序列问题， 同样，QA也可以被视为是将
代表问题的一组字序列映射成一组代表答案的一组字序列。所以，很显然，一种独立于某种领域的map sequence to sequence的方法
是很有用的.**很多问题上它不行**

Despite their flexibility and power, DNNs can only be applied to problem whose inputs and targets can be 
encode with vextors of fixed dimensinality. It is a significant limitation, since many important problems 
are best expresses with sequences whose lengths are not known a-prior. For exemple, speech recognition and 
machine translation are sequentia problems. Likewise， QA can alse seen as mapping a sequence of words rep-
resenting the question to a sequence of words representing the answer. It is therefor clear that a domain-in-d
ependent method that learns to map sequences to sequences would be useful.

序列给DNNS提出了挑战因为DNNS需要输入和输出的维度是已知和固定的。 本文中， 我们展示一个简便的LSTM的应用可以解决广义的
sequence to sequence 问题。idea 是用一个LSTM来读一个输入序列，one time at a time， 来获得large fixed dimensional vector representation, 
然后用另一个LSTM从这个向量中提取输出序列。第二个LSTM本质上是一个循环神经网络语言模型except that it is conditioned on 
the input sequnce. LSTM 在具有长距离依赖关系是大规模数据上的学习能力使之成为此应用的当然之选由于输入和输出之间存在相当大的时间滞后

sequence pose challenge for DNNS because they are require that the dimensionality of input and output is 
known and fixed. In this paper, we show a straightforward application fo the LSTM  can solve general sequnce
to sequence problem. The idea is to use a lstm read the input sequence, one time at a time, to obtain large
fixed dimensional vector representaion, and then to use another lstm to extract output sequence from the vector
. THe second LSTM is essentially a recurrent neural network language model . The lstms ability to learn on data
with long range temporal dependencies makes it a natural choice for this application due to the cosidertable
time lag between the inputs and their corresponging outputs


