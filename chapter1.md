# Lasso

索套回归

### 

### 目标函数：

#### $$\underset{w}{min\,} { \frac{1}{2n_{samples}} ||X w - y||_2 ^ 2 + \alpha ||w||_1}$$

其中，$$||w||_1$$为L1范数

### 

### 正则化参数（alpha）的设置：

* #### **cross\_validation 交叉验证：**

```
   分为 LassoCV 、LassoLarsCV
   
   lassoCV 采用 “坐标轴下降法” 优化损失函数，对于多重共线的高维特征数据，lassoCV是第一选择。
   
   lassoLarsCV 采用 “最小角回归法” 优化损失函数，lassoLarsCV是第二选择，速度比lassoCV快。
   
   lassoLarsCV 应用场景一：如果想探索超参数α更多的相关值，由于最小角回归可以看到回归路径，此时用LassoLarsCV比较好。
   
   lassoLarsCV 应用场景二： 如果我样本数远小于样本特征数的话，用LassoLarsCV也比LassoCV好。
   
   其余场景最好用LassoCV。
```

* #### LassoLarsIC 

```
采用AIC、BIC 做验证，可以一轮找到alpha值，相比K折交叉检验需要K+1，速度更快。

使用lassoLarsIC需要对解的自由度做一个适当的估计。且该估计需来自大样本，并假设该模型是正确的。

当待求解的问题条件不满足时（如，特征数大于样本数），准则会有崩溃的风险。

因此，只有在数据来自一个模型确定的大样本，且样本数量足够大时，才能用 lassolarsIC。

```



