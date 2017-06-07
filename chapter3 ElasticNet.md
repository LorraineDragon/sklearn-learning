# Elastic Net

弹性网络

### 

### 目标函数：

### $$\underset{w}{min\,} { \frac{1}{2n\_{samples}} \|\|X w - y\|\|\_2 ^ 2 + \alpha \rho \|\|w\|\|\_1 +

\frac{\alpha\(1-\rho\)}{2} \|\|w\|\|\_2 ^ 2}$$

其中，$$p$$ 为范数权重超参数

ElasticNet 可以看作 Lasso 和 Ridge 的中庸产物，损失函数用一个权重参数 $$p$$ 来平衡 L1 和 L2 正则化的比重。

