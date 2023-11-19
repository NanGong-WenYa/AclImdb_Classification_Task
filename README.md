# 基本说明
* 本项目是基于HuggingFace提供的transformers库中的bert-base-cased模型对aclImdb的影评。
* 文本做情感二分类的处理。

# 运行环境
* conda 23.9.0
* pytorch 2.1.0
* CUDA 12.3
* GPU NVIDIA GeForce RTX 3060 Laptop GPU

# 训练参数
* pretrained_model: bert_base_cased
* epoch: 10
* batch_size: 120
* optimizer: AdamW
* criterion: CrossEntropyLoss
* tokenizer: truncation=True, max_length=500, padding=max_Length
* dataset: IMDB (trainset 25000条，testset 25000条）

# 训练成果
## 训练集：
* Epoch 1/10
  * Iteration 0, Loss: 0.6752526164054871, Accuracy: 0.6333333333333333
  * Iteration 10, Loss: 0.6776291131973267, Accuracy: 0.6666666666666666
  * Iteration 20, Loss: 0.6820762157440186, Accuracy: 0.5833333333333334
  * ...（中间省略）
  * Iteration 200, Loss: 0.6319226026535034, Accuracy: 0.7166666666666667
* Epoch 2/10
  * Iteration 0, Loss: 0.6330417394638062, Accuracy: 0.7416666666666667
  * Iteration 10, Loss: 0.6086034774780273, Accuracy: 0.7833333333333333
  * ...（中间省略）
  * Iteration 200, Loss: 0.5158011317253113, Accuracy: 0.7833333333333333

## 测试集
* Accuracy: 0.77125

## 结果分析
* 收敛情况：训练集准确度逐渐增加表明模型在训练时学习到了数据的特征，并在测试集上表现良好，这说明模型没有出现严重的过拟合。
* 局限性分析：考虑到数据集规模和模型复杂性，可能还有进一步提高模型性能的空间。尝试调整超参数、增加数据量或尝试其他预训练模型。
* 可行性：模型在测试集上的表现较好，还需对其性能进行更深入的评估和测试。
