# 构建学生成绩预警系统

------
## 项目背景
随着教育行业对科技的依赖与日俱增，有越来越多的数据可用于检验和预测。现在，通过像 Canvas 和 Edmodo 这样的学习管理系统，可以即时收集并使用学生活动、分数、与教师和同学的互动等记录。这对于在学校中（甚至是初中和高中）越来越流行的网上教室尤为如此。

在各级教育中，相关人士努力帮助提高学生成功的可能性，同时确保不削弱教育力度，或者不做出此类举动：在未改善实际的基础学习水平的情况下，提高学生通过考评的可能性。就此而言，毕业率通常是选择标准，而且教育者和管理者正寻找新的方法尽早预测学生的成功和失败（早到足以实施有效的干预以及确定不同干预措施的效果）。

## 客户目标与要求
当地学区的目标是，通过在学生退学前识别需要干预的学生，在这个十年结束时让毕业率达到 95%。但是，由于资源和预算有限，校监会希望能在最大限度节省计算费用（按照在服务器上使用的内存和 CPU 时间向该公司付费）的情况下找出最有效的模型。

## 解决方案及结果
运用监督学习来为预测学生有多大可能通过高中期末考试的相关因素建立模型。
### 使用的语言和库
> * Python
> * Numpy
> * Sklearn


### 分析与学生的表现有关的数据集

> * 学生总数: 395
> * 特征数: 30
> * 顺利毕业人数: 265
> * 未能毕业人数: 130
> * 通过率: 67.09%

### 处理原始数据并构建合适的模型
将非数字类数据转化为数字类别，划分数据集/测试集，分别构建 **K 近邻**、**SVM** 和 **逻辑回归**三种分类模型 ,根据计算量（训练模型及测试所用时间）及预测效果（训练集及测试集的 F1
分数）,最终选择**SVM** 作为最佳模型。

### 模型调优及结果
利用Sklearn库中的GridSearchCV和make_scorer工具进行**SVM**模型参数调优，最终结果为数据集的F1分数为 0.9710，测试集的F1分数为0.8205。