# 0 赛题链接
[报名链接](https://challenge.xfyun.cn/topic/info?type=text-detector&option=ssgy&ch=ymfk4uU)
# 1 赛题介绍

## 1.1 实践任务
参赛选手需要对输入的匿名的文本进行类别来源的判断。
- 输入：文本序列
- 输出：文本类别

数据分为name(id), label(标签)，content(内容，疑似文本序列化后的产物)

![数据截图](https://img.ziuch.top/i/2023/09/01/image-2.png)
content数据分析结果
![content数据分析结果](https://img.ziuch.top/i/2023/09/01/image-2_1.png)

## 1.2 数据集解析
数据集为中文作文样本，其中从互联网上采集得到了真实作文，并且ChatGLM-6B生成了部分作文。参赛选手的任务是根据文本内容，区分作文的来源。

# 2 实践思路
文本分类是自然语言处理（NLP）中的一个重要任务，其作用是将输入的文本按照预先定义的类别或标签进行分类。在文本分类中，我们通过使用计算机算法和机器学习技术，使计算机能够自动地将大量的文本数据归类到不同的类别中，从而帮助我们更好地理解和组织文本数据，以及从中获得有用的信息。文本分类的思路和步骤通常可以概括为以下几个主要步骤：

1. **数据收集与预处理**： 首先，需要收集用于文本分类的数据集。数据集应包含已标注好的文本样本，每个样本都对应一个预定义的类别或标签。在预处理阶段，对文本数据进行清洗、分词、去除停用词和特殊字符等操作，以便为后续的特征提取和模型训练做准备。
2. **特征提取**： 特征提取是将文本数据转换为计算机可处理的数值表示的过程。常用的特征提取方法包括词袋模型（Bag of Words）、TF-IDF（词频-逆文档频率）、Word2Vec、BERT（Bidirectional Encoder Representations from Transformers）等。这些方法能够将文本数据转换为向量形式，保留了文本的语义和语法信息。
3. **建立分类模型**： 在特征提取之后，我们需要选择一个适合的分类模型来训练。常见的分类模型包括朴素贝叶斯（Naive Bayes）、支持向量机（Support Vector Machine, SVM）、逻辑回归（Logistic Regression）、决策树（Decision Tree）、随机森林（Random Forest）和深度学习模型如卷积神经网络（Convolutional Neural Networks, CNN）和循环神经网络（Recurrent Neural Networks, RNN）等。
4. **模型训练**： 将预处理后的特征数据输入选择的分类模型，并对模型进行训练。在训练过程中，模型根据已标注的数据样本进行学习和优化，调整模型的参数以最小化分类错误。
5. **模型评估**： 使用测试集来评估训练好的模型的性能。常见的评估指标包括准确率、精确率、召回率、F1 分数等。
6. **调优优化**： 根据评估结果，可以对模型进行调优优化，以提高模型的性能。调优方法包括调整模型参数、优化特征提取过程、尝试不同的分类模型等。

# 3 实践代码
- 采用传统的机器学习方法，人工提取特征和TF-IDF特征，使用逻辑回归模型/SVM模型/决策树模型/随机森林模型进行训练，最终使用逻辑回归模型进行预测。
- 采用深度学习方法，使用BERT模型进行训练，最终使用BERT模型进行预测。
详见代码