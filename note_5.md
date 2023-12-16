# 大模型的训练数据：原始文本
google索引100PB

1PB = 1024（$2^10$）TB，以此类推 GM MB KB B

GPT-2：WebText 40GB，OpenWebText38GB

C4:806GB

The Pile:825GB较小高质量数据集

# 分词
1. 空格分词
2. Byte pair encoding(BPE):合并频率最高的元素对
3. Byte-level BPE(BBPE):抵抗unicode稀疏
4. unigram moel:目标函数不是出现频率，使用似然度：分词出现概率之积。计算loss(x)，筛选出似然度loss大的数据。
