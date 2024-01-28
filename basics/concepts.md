1. batch的含义和意义
    实际神经网络训练中数据量往往很大，如果所有数据一起进行梯度下降计算梯度，是十分耗时的，所以会将数据分成多个batch，一个batch算一个loss，更新一次参数，所有batch训练完，成为1个epoch。
    batch_size也是nn的超参，batch的大、小各有优势：batch小，training loss(optimization)、testing loss(generalization)更好，但一个epoch训练的时间要更长。cuz: batch小，各个batch的优化方向不同，train的时候反而更容易找到最优点，同时在testing的时候，由于和train的数据分布不同，batch大的loss可能更大。
    
    others answer: batch的思想，至少有两个作用，一是更好的处理非凸的损失函数，非凸的情况下， 全样本就算工程上算的动， 也会卡在局部优上， 批表示了全样本的部分抽样实现， 相当于人为引入修正梯度上的采样噪声，使“一路不通找别路”更有可能搜索最优值；二是合理利用内存容量。

2. batch的情况下如何更新参数？
