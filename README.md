# 文件结构说明

## data:
存放数据包weather,包括了全球30个城市1994-2014年的气候信息数据，可用于评测该模型的准确率

## record:
存放实验数据(主要为图片数据),具体说明如下：

### single model:
最简单模型，即不考虑竞争和共生的条件下对温度为27℃、干燥度为0.25下真菌增长率、数量变化和木质纤维分解效率的变化

### compare_relation_influence：
对比实验说明竞争、共生的存在对多种群真菌分布的影响

### competition_model：
竞争模型下的真菌增长率、数量变化和木质纤维分解效果的数据记录，按照马瑙斯、洛杉矶、福特斯、吐鲁番和西雅图（分别代表热带、半干旱、树栖、干旱和温带气候）的顺序记录数据，并附有五个地方的真菌分解效果图,其中的data.txt是对Figure_7中五个城市垃圾降解半衰期（这里姑且称作半衰期）的采点，顺序记录同图例顺序

### sysmbiosis_model:
共生模型下的真菌对木质纤维分解效果的数据记录，由于共生的种群数目较少，对总体模型的影响稍微较小

### different_environment_influence：
记录了不同环境温度和干燥度下真菌增长率、数量变化和木质纤维分解效率的变化，以30个种群和70个种群做实验，实验环境如下：
1.温度以0℃为均值，方差为3变动；
  干燥度以0.5为均值，方差为0.1变动
2.温度以0℃为均值，方差为10变动；
  干燥度以0.5为均值，方差为0.2变动

### different_number_of_fungi：
记录了相同环境温度和干燥度下真菌增长率、数量变化和木质纤维分解效率的变化，以10个种群和70个种群做实验，实验环境如下：
温度为27℃；干燥度为0.25

### predict_type_of_weather：
根据模型推演真菌数量变化，与以作标记的label_weather文件夹下记录的五个城市的真菌（与推演真菌的类型相同，图中颜色相同者为同一类）数量、分解率等关系的实验图为基准，判断当地的气候条件。

### predict_type_of_the_strongest_one_in_the_environment:
根据已知气候类型和温度、干燥度环境，预测最优势种群，并和实际模型推理结果作对比（即评估）

## fnugi.py + dataset.py + Q1.py :
python语言实现文件