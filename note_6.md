# 模型架构
 embedding:嵌入函数，将上下文表示为向量
 ## 分类
### encoder:
- BERT:生成向量，做分类（自然语言理解）任务
- 依赖左右两侧
### decoder:
- GPT:自回归语言模型
- 依赖左侧生成

### encoder-decoder:
- Transformer

## 模块
### 基础架构
- embed token:将标记转换成向量
 ![image](https://github.com/melonlala/so-large-lm/assets/108521058/54eca974-585b-4abf-aca7-f9be55b8eb6c)

- sequence model:将enbedding映射为与上下文相关的
  ![image](https://github.com/melonlala/so-large-lm/assets/108521058/85f3d9cc-08ff-48c8-9947-cd264fea7fdd)

  eg: 前馈序列Feed Forward Sequence Model:查看前n个元素
### 序列模型：递归神经网络（RNN、LSTM、GRU）
- 通过简单的线性变换和非线性函数根据新的观测值 x 更新隐藏状态 ℎ
- 双向
### Tramsformer:
- 注意力机制：y与每个$x_i$对比生成对应的注意力分数，再进行加权
- 多注意力头是进行多次比较
- 自注意层SelfAttention：使用x替换y进行查询
- 前馈层FeedForward：连接不同标记
  ![image](https://github.com/melonlala/so-large-lm/assets/108521058/b06bf3ac-5d23-430c-8c22-4cfba1236fe7)

- 加入残差连接和归一化：AddNorm函数
- Transformer Block:![image](https://github.com/melonlala/so-large-lm/assets/108521058/18fd6b2f-9e9d-4383-a38a-25bc2d2221f4)
- Position Embedding位置嵌入![image](https://github.com/melonlala/so-large-lm/assets/108521058/bd5b3e99-b994-4cc1-a7df-4768c81fa047)
- GPT3: 96次引入位置嵌入的Transformer层

- 差异：归一化先后、dropout防过拟合、稀释、不同掩码
