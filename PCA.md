# PCA

Principal components analysis，主成分分析

非监督学习的降维方法。主要用于数据降维，消除冗余和噪音。

### 优点

* 仅以方差衡量信息量
* 各主成分正交，可消除原始数据间的相互影响
* 计算方法简单

### 缺点

* 含义模糊，解释性不如原始样本
* 方差小的非主成分可能含有重要信息，因降维会被丢弃

# KPCA

对于非线性数据，不能直接用PCA降维，需要用到核函数的思想。先把数据集从n维映射到线性可分的高维N&gt;n,然后再从N维降维到一个低维度n', 这里的维度之间满足n'&lt;n&lt;N。通过在高维空间进行协方差矩阵的特征值分解，然后用和PCA一样的方法进行降维。

# sklearn

与PCA相关的类都在sklearn.decomposition\(分解\)包中。

PCA 最常用

KernelPCA 非线性核方法的KPCA

IncrementalPCA 解决内存问题

SparsePCA、MiniBatchSparsePCA 使用L1正则化，仅需要对相对重要的成分进行降维，避免噪音。

* 共性：两种方法都需要对L1正则化参数进行调参

* 区别：MiniBatchSparsePCA使用一部分样本

## sklearn.decomposition.PCA

一般不需要调参。

只需要指定降维的维度，或者降维后主成分方差和占原始数据方差和的比例阀值。

### n\_components

指定降维后的特征维度数目

可以指定为维度数，int&gt;1

可以指定为方差和所占最小比例阀值，（0，1】

mle，用mle算法根据特征方差分布自己选择

默认，n\_components=min\(样本数，特征数\)

### whiten

是否进行白化，即对降维后的数据的每个特征归一化。

一般不需要，默认false

### svd\_solver

指定奇异值分解的方法{’auto‘，’full‘，’arpack‘，’randomized‘}

randomized 适合数据量大，数据维度多，主成分数目比例较低，加入了加快SVD的随机算法

arpack 与randomized类似，区别是调用了scipy

full 传统意义上的svd，使用scipy库对应实现

auto，默认值，一般不需要修改

### **explained\_variance**

降维后各主成分的方差值。方差值越大，说明越重要。

### **explained\_variance\_ratio\_**

降维后各主成分的方差占总方差的比例，比例越大，越重要



