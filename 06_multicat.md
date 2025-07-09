1. How could multi-label classification improve the usability of the bear classifier?
因为有时，分辨不出来，直接用None表示就好了
   
2. How do we encode the dependent variable in a multi-label classification problem?
标签数据采取的是one-hot编码，保证向量维度一致

3. How do you access the rows and columns of a DataFrame as if it was a matrix?
采用 df.iloc[:,0], df.iloc[0,:] 

5. How do you get a column by name from a DataFrame?
df['name']

6. What is the difference between a Dataset and DataLoader?
Dataset 包含一个train dataset 和一个 valid dataset 数据集划分，根据DataBlock加载数据存储样本，数据容器
DataLoader 包含一个train dataloader 和一个 valid dataloader,基于dataset工作，批量加载，打乱顺序，并行加载等，是连接dataset与模型的管道

7. What does a Datasets object normally contain?
训练集和验证集

8. What does a DataLoaders object normally contain?
train dataloader，valid dataloader, 数据预处理管道信息,包含数据块（DataBlock）中定义的预处理逻辑（如图像大小、数据增强方式、标签格式转换等,
数据集元信息,如特征和标签的类型（如图像、类别、坐标）、批次大小（batch size）等，用于协调模型输入与数据格式的匹配。

9. What does lambda do in Python?
匿名函数，lambda x: return f(x) 

10. What are the methods to customize how the independent and dependent variables are created with the data block API?
在 FastAI 的数据块 API（DataBlock API）中，自定义自变量（输入数据，如图像、文本）和因变量（标签，如类别、坐标）的创建方式，主要通过以下核心方法实现：
1. get_x 和 get_y 参数
2. blocks 参数指定数据类型，处理自变量和因变量的数据类型
  - ImageBlock：处理图像数据（自变量）。
  - CategoryBlock：处理分类标签（因变量，如类别名称）。
  - PointBlock：处理坐标标签（因变量，如关键点坐标）。
  - RegressionBlock：处理回归任务的数值标签。

11.Why is softmax not an appropriate output activation function when using a one hot encoded target?

12.Why is nll_loss not an appropriate loss function when using a one-hot-encoded target?

13.What is the difference between nn.BCELoss and nn.BCEWithLogitsLoss?

14.Why can't we use regular accuracy in a multi-label problem?

15.When is it okay to tune a hyperparameter on the validation set?

16.How is y_range implemented in fastai? (See if you can implement it yourself and test it without peeking!)

17.What is a regression problem? What loss function should you use for such a problem?
预测的结果是数值
18.What do you need to do to make sure the fastai library applies the same data augmentation to your input images and your target point coordinates?
使用PointBlock 定义目标点坐标的类型
