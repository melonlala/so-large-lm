# 模型训练
## 目标函数
### decoder-only: 
- eg:GPT3
- 单向上下文嵌入，一次生成一个token
- token->嵌入->打分->预测分布![image](https://github.com/melonlala/so-large-lm/assets/108521058/52ceff8b-4064-4966-942d-a9e8a4508d7e)
- 目标：最大似然分布概率![image](https://github.com/melonlala/so-large-lm/assets/108521058/cb711fd4-fd6b-4c63-9779-0e97a1bb075b)
- 将分类转换成生成
### encoder-only:
- eg:BERT，双向：不生成
- CLS，SEP分割输入![image](https://github.com/melonlala/so-large-lm/assets/108521058/e307cd06-9d94-4c68-94e7-b162ec6a035b)
- ![image](https://github.com/melonlala/so-large-lm/assets/108521058/35c4242b-0a5d-43d6-9a77-b6644ddd6f54)
- 掩码语言模型：去噪自动编码器， 随机加mask or 原词，重建（通过嵌入CLS来分类）
- 下一句预测：预测随机生成or原始句子是否为下一句（RoBERTa删去，它没用）
- ![image](https://github.com/melonlala/so-large-lm/assets/108521058/cd0ad139-6a69-4c45-bea9-a1d35220de07)

### encoder-decoder:
- 表格生成文本：双向编码，再自回归解码
- BART：掩码+打乱子句（不懂）
- T5：text2text transfer tansformer预训练任务： 给定一段文本，在随机位置将其分割为输入和输出, 整理了pipeline

## 优化算法
1. SGD
2. Adam
3. AdaFactor
4. 混合竞速
5. warmhot学习率
6. 
