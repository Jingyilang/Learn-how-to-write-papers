ACL2017-1125
## Abstract
中国诗歌被证明可以成功地有sequence-sequence 神经模型生成（**引入任务，同时介绍了目前方法**）。但是，这种方法的潜在问题是神经模型仅仅能学习抽象规则，而诗歌的生成是一个高度创造性的过程，并不仅仅涉及规则还涉及创新，纯粹的统计模型原则上并不适合(**目前方法的不足**)。本文提出一个用于汉语诗歌生成的建议增强模型， 其中神经模型和增强记忆模型合作老平衡语言一致性和审美创新的需求，使得创新性的生成依然兼容规则（**简要介绍本文方法**）。 另外，结果发现，建议机制提供了有趣的灵活性，可以被用来生成不同类型的诗歌。

It is shown that Chinese poem can be successfully genetated by  sequence-to-sequence neural model. The potential problem of this method, however, is that neural midels can only learn abstract rules,while poem generation is a highly creative process that involves not only rules but also innovations for which pure statistics models are not appropriate in principle. This work proposes a memory-argument neural model for Chinese poem generation, where the neural model and the augmented memory work together to balance the requiress of liguistic accordance and aesthetic innovatio. , leading to creative generations that are still rule-compliant. In addition, it si found that, memory mechanism provides interesting flexibility that can be used to genetate poem with different styles.

## 1 introduction
中国古典诗歌是一个特殊的超过2000的文化遗产，今天依然吸引着我们。 在不同的体裁中，可能最流行的是绝句quatrian， 一种有着严格结构的特殊类型（四行，每行五或七字）,(引入、介绍任务，这里面可以写意义，难点)

本文我们对机器诗歌翻译感兴趣。 研究人员已经提出几种方法。 比如。。。，相较于以往的方法（比如rule-based or SMT), 神经模型往往能生成更流利的诗歌，有些生成是如此的自然以至于专业的世人都不能说这是机器的工作。

In this paper we are interesting in machine poetry generation. Several methods have been studies by researches, for example... Compared to previous methos, the neural model tends to generate more fluent poems and some generations are so nature that professional pots can not tell they are works of machines.

尽管有这些理想的结果， 神经模型在诗歌生成中也有特定的问题 缺乏创新。 由于神经模型的统计特性， 他们更专注于高概率的模式，而忽略了低频率模式， 换句话说， 模式越规律和普通，神经模型越能学习他们 在run-time更倾向于频繁的使用它们。这种特性确实能帮助生成更流利的句子，但是并不总是有用。帅哥的最大价值不是流利，
而是可以激发一些独特感觉的审美创新.这对富于紧凑和表达力的中国绝句来说尤其如此：在几千年的历史中，此体裁几乎不可能发现两个相似的作品， 证明了独特性后者说创新的重要性。具有讽刺意味的是， 最重要的事，创新，如果不是因为噪声的话，对于现在的神经模型来说，在很大程度上被视为是微不足道的。（**现存方法的不足**）

In spite of these results, neural models suffer from particular problem in poem generation, a lack of innovation. Due to the statistics nature of neural models, they pay much more attention to high-frequency pattern, whereas they ignore low-frequency pattern. In other word, the more regular and common the pattern, the better the neural model is good at learing them  and tend to use them more frequencyly at run-time. This property certainly helps to generate fluent sentence, but it is nor always useful: the major value of poems in not fluency, but the aesthetic innovations that can stimulate some unique feelings.This is particularly true for Chinese quatrains that are highly compact and expressive. It is nearly impossible t find two similar words in the thousands fo years of history in this genre, demonstrating the importance of uniqueness or innovation, Ironically, the most important thing, innovation, is largly treated as trival, if not noise, by present neural models.

事实上这个问题呗所有的基于统计的生成模型所共有（尽管在神经模型中更严重）, 长久以来引起了对机器诗的批评：它可以作， 有时候也作的很好，但是作品往往不够新奇也不有趣， 更严重的是， 这个问题并不仅仅存在于诗歌生成中，也存在于所有需要创新的生成任务中。

Actually this problem is shared by all generation models based on statistics(although it is more serious for nertal models)， and has aroused a long-standing criticism for machine poem genneration: it can generate, and sometimes generate well, but the generation tend to be unsurprising and not particularly interesting, . More serously, this problem exists not only in poem generation , but also in all generation tasks that require innovation.  

本文试图去解决这个十分具有挑战性的问题，我们认为最关键问题是统计模型善于学习通用的规则（常用单词和他们的组合的用法）但是缺乏记住特殊instances的能力，其很难被通用规则所覆盖。 换句话说，只有基于规则的推理，没有基于实例的记忆。所以我么提出一个memory-augmented 神经模型，该模型涉及一个神经记忆，所以特殊的实例可以被保存 在run-time被使用.在就像人类诗人不仅参考通用规则和模式，也在会议以前读过的诗。 很难说这种规则和实例的结合产出了真正的创新（这经常需要真实生活的激励而不是简单的词语重组）， 但是这确实提供了有趣的灵活性来生成新的输出，这种输出看起来具有创造性而且依然兼容规则。 更重要的是， 这种灵活性可以被用与其他方法中，比如用不同的风格在生成诗句。

This paper tries to solve the extremely challenging problem, we argue that the essential problem is statistics model are good at learning general rules(), but less capable of remember special instances that difficult to cover with general rules. In other word, there is only rule-based reasoning, no instance-based memory. We therefore present a memory-augment neurla model that involves a neural memory so that special instance can be saved and referred to at run-time. This is like human poet who creats poems by not only referring feneral rules and pattern, but also recalls poems that he has read before. It is hard to say whether this combination of rules and instance produces true innovation((, It indeed offers interesting flexibility to generate new output that look creative and are still rule-compliant. Moreover, this flexibility can be used in other ways, e.g.generating poems with different styles.
