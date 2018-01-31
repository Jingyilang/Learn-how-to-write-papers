## Introduction
Approximate nearst neghbor(ANN),伴随着在信息检索、计算机视觉等领域的诸多应用，吸引了机器学习界的更多
关注。作为ANN最广泛使用的技术，hashing致力于将data point 编码成密集哈希码. 由于其储存和搜索的高效性， 
hashing 吸引了越来越多的关于大规模ann研究的关注。

ANN has attached much attention from machine learning community with a lot of applications in infor
retrieval. computer vision and so on. As a widely used technique fo ANN, hashing aims to encode the data
point to compact hashing code. Due to the its storage and search efficiency, hashing has attracted
more and more attention for large scale ANN search.

作为前期的工作， LSH试图采用随机过程作为哈希函数。 类LSH方法一直被称为数据无关方法，因为随机工程通常是与训练数据无关的
。 相反的是， 数据有关方法，也被称为学哈希方法，志在从训练数据中学习哈希函数。数据有关方法通常相比数据无关取得了更加
理想的效果。因此，数据有关方法在近几年比数据无关方法更加流行。 基于十分用到监督信息，数据有关方法可以进一步的分为两类：
无监督哈希和有监督哈希。无监督哈希不为哈希函数的学习使用监督信息， 相反的是， 监督哈希通过采用监督信息来学习哈希函数。 最近
几年， 监督哈希得到了越来越多的关注因为它可以比无监督学习取得更好的准确率。

As the pineering work, LSH tried to utilize random projection as hash function. LSH-like methods are always called
data-independent methods, because random projection are typically independent of training data. On the contrary, 
data-dependent methods, which is alse called learning to data methods, aims to learn hash function from trainig dta
data-dependent methods usually achieve more promising performance than data-independent methods. Hence, data-dependent
methods have become more popular than data-independent methods in recent years. Based on whether supervised infor
is used or not, data-dependent methods can be further divided into teo categories:unsupervised hashing and supervised
 hashing. Unsupervised hashing does not use supervised infor for hash function learning. On the contrary, supervised
 hasing tries to learning hash function by utilizing supervised information. In rencent years, supervised hasing
 has attracted more and more attention because it can achiece better accuracy the unsupervised hashing
 
 许多传统的监督哈希方法都不少深度方法，其不能从scratch 中执行特征学习。 最近，深度监督哈希，即采用深度学习来为哈希执行特征学习
被研究者提了出来。 代表性的深度监督哈希方法包括了基于CNN哈希， 。。。通过将特征学习和哈希编码整合进同一的端到端结构， 
深度监督哈希可以在应用上很大程度上超过non-deep， 监督哈希。
most tranditinal methods are non-deep methods, which cannot perform feature learning from scratch. Recently, 
deep supervised hashing, which adopts deep learning to perform feature learning, proposed by researchers.By
integrating feature learning and hash-code into the same end-to-end architecture. Deep supervised hash can 
significantly outperform non-deep supervised hash in many applications.

许多现存的深度监督哈希方法，包括以上提到的方法，
