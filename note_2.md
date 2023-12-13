## Adaption: 从语言模型到任务模型
* 输入输出对
* 有监督训练 or prompt(上下文学习)： 微调， prompt受限于tramsformer
## 评估gpt3: 消融模型大小与prompt数量
### 任务一：模拟语言
1. 指标：困惑度
   *几何平均替代算术平均惩罚低概率，
   * 可理解为在每个位置模型认为有多少种可能出现词数的平均值
  ![image](https://github.com/melonlala/so-large-lm/assets/108521058/a727e35e-f225-4bc8-ae48-edb1ec491001)
   * 惩罚召回错误（为正确值分配低概率）， 精确度错误（为错误分配高概率）惩罚不足
2. 实例：
   * Penn Tree Bank：直接给困惑度，应该没有泄露
  * LAMBADA：填空，需要prompt
  * HellaSwag:选择题（常识推理）：长度or频率归一化，未归一化倾向于短答案。(gpt3 fail)
### 任务二：回答问题
1. TriviaQA： 模型大小与prompt数量都有用
2. WebQuestions：gpt3 fail
### 任务三：翻译
1. 标准的评估数据集比如是WMT’14和WMT’16数据集
2. 评估指标是BLEU
3. few-shot很好，
4. 法语和罗马尼亚语的结果类似。英语到外语差
### 任务四：算术
1. 模型大小有用
### 任务五：新闻标题生成（总结）
1. 人类52%能区分：这里的评估标准不好


