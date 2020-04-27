# 数据挖掘从入门到进阶

## pandas教程

绝佳的开源实践课程：
https://mp.weixin.qq.com/s/Em9gZehlYQ-SLp75AUre5g

## 冠军思路
https://mp.weixin.qq.com/s/TzFB0GmL10r3ZKDDkB8x_A

## 知识整理
该知识整理内容仅为**复盘知识整理**部分，详见[知识整理](./知识整理.md),以下为零基础入门数据挖掘之二手车预测大赛笔记的文档，详细流程见[@夏凡](https://gitee.com/sovlookup/ai_learning_notes/tree/master/%E9%9B%B6%E5%9F%BA%E7%A1%80%E5%85%A5%E9%97%A8%E6%95%B0%E6%8D%AE%E6%8C%96%E6%8E%98%E4%B9%8B%E4%BA%8C%E6%89%8B%E8%BD%A6%E9%A2%84%E6%B5%8B)的gitee仓库

另外附上400分的大佬的notebook：
https://tianchi.aliyun.com/notebook-ai/detail?spm=5176.12586969.1002.21.1cd866c2rkS6gt&postId=103212

---

本打卡笔记根据官方[baseline][6]修改而来，天池赛题链接：https://tianchi.aliyun.com/competition/entrance/231784/introduction?spm=5176.12281949.1003.3.493e593auHLYrb

笔记特点：

 - **详细的、整理过的全部流程**
 - **使用nni搜索超参**
 - **本流程LGB得分522**
 - **相关知识点资料已经整理完毕**
  
注意要点：

- **模型已经保存在链接：https://pan.baidu.com/s/1uE6JoqWaF7yQD9fqUbF58w 提取码：9unh 读取方法见[模型读取.txt]**
- **各类导出数据已上传[Kesci][2] ./XXX_data下的数据使用前请解压**
- **脚本中引用路径请自行修改**

资料链接：

1. [打卡活动中整理的资料](https://pan.baidu.com/s/1yPCU1nqYNikv5k4lGQg-fw)
提取码：it09


PS:资料来源于datawhale官方和参加打卡的小伙伴的笔记分享等
-------------------


## TASK1

[赛题理解][5]


## TASK2&3


[EDA与特征工程][4]

## TASK4

建模调参

比较喜欢科学调参，所以就用NNI进行了超参搜索

1. lgboost
2. xgboost
3. RandomForestRegression

## TASK5
模型融合

---------


[2]: https://www.kesci.com/home/dataset/5e7f1c5f246a590036b7907c/files

[4]: https://tianchi.aliyun.com/notebook-ai/detail?postId=95501


[5]: https://tianchi.aliyun.com/notebook-ai/detail?spm=5176.12586969.1002.18.1cd8593afOsgSs&postId=95456


[6]: https://tianchi.aliyun.com/competition/entrance/231784/forum

