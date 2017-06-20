# Elastic Net

弹性网络

ElasticNet 可以看作 Lasso 和 Ridge 的中庸产物，损失函数用一个权重参数 $$p$$ 来平衡 L1 和 L2 正则化的比重。

### 

### 目标函数：

### $$\underset{w}{min\,} { \frac{1}{2n_{samples}} ||X w - y||_2 ^ 2 + \alpha \rho ||w||_1 +\frac{\alpha(1-\rho)}{2} ||w||_2 ^ 2}$$

其中，$$p$$ 为范数权重超参数



### 超参数的确定：

用 ElasticNetCV 确定参数 alpha 和 $$p$$，使用的是交叉验证。

使用场景：Lasso 稀疏特征过多，Ridge 回归系数衰减太慢。







