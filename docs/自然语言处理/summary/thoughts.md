 ## 项目报告阅读笔记

知识驱动情报智能应用建设

### 基本

| 序号 | 项目流程           | 创新点/难点                |
| ---- | ------------------ | -------------------------- |
| 1    | 数据获取           | 多样大量丰富新鲜的一线数据 |
| 2    | 信息抽取识别       | 图神经网络方法             |
| 3    | 图与时空数据的储存 | 充分利用时空数据           |
| 4    | 数据利用           | 知识推理和图数据分析       |

### 拓展

| 序号 | 项目目标                                     | 技术难点                            | 解决对策             | 参考技术   |
| ---- | -------------------------------------------- | ----------------------------------- | -------------------- | ---------- |
| 1    | 顾及时空特征的缉私知识表达模型               | 实体和关系需要绑定时间序列与GIS信息 | 采用新数据库         | 事理图谱   |
| 2    | 缉私情报研判模型的自动生成                   | 关系图谱间隐藏关系的推理            | 引入知识推理算法     | 知识推理   |
| 3    | 研发适用于缉私知识获取管理与业务化应用的平台 | 信息化建设应用                      | 需要建设维护一套平台 | 图数据分析 |
| 4    | 利用图神经网络等方法更好地处理非结构化数据   | 图神经网络应用                      | 利用工具             | 信息抽取   |

#### 文献阅读

##### 35 40号论文研读总结

###### 两篇论文有相同的架构流程：

论述　->　建设数据层　->　建设模式层　->　可视化

###### 使用相同的工具：

neo4j protege deepfinder

推理功能不足

#### 思考

##### 优点

1. 这两篇论文具有相同的写作模式（流程和工具），这种模式可以参考

2. 有丰富的论文引用，可以继续探究

3. 将知识图谱与公安实践结合的理论可以借鉴

4. 相关技术模型可以借鉴

##### 缺点

1. 模式上固化，模式层和数据层可以交叉建设，是反复迭代的过程
2. 有些地方过于简略，比如知识推理的部分
3. 没有应用实效，代码过程没有开源，论文缺少深度挖掘借鉴的能力
4. 利用的工具为闭源产品，不安全 无拓展性，并且相对过时，不符合当前实践条件

#### 已有资源

##### 自然语言处理工具

1. NLTK：https://github.com/nltk/nltk
2. 图数据元学习：https://github.com/THUMNLab/AutoGL
3. 文本数据元学习：https://github.com/awslabs/autogluon
4. 百度nlp开箱即用工具集：https://nlp.baidu.com/homepage/nlptools｜https://github.com/PaddlePaddle/models/tree/develop/PaddleNLP
5. 一个小玩具snownlp：https://github.com/isnowfy/snownlp
6. 百度分词，词性标注，命名实体识别：https://github.com/baidu/lac
7. 百度情感分析：https://github.com/baidu/Senta
8. 百度开源的依存句法分析系统：https://github.com/baidu/DDParser
9. 信息抽取工具集（抽出三元组）：https://www.jianshu.com/p/a1994336af2d
10. 中文命名实体识别和关系抽取：https://zhuanlan.zhihu.com/p/268625650

##### 社区

中文开放知识图谱：http://openkg.cn/home

##### 大佬

中科院刘焕勇：https://liuhuanyong.github.io/

##### 项目

1. 罪名法务问答：https://github.com/liuhuanyong/CrimeKgAssitant
2. 相似案件匹配：https://github.com/padeoe/cail2019
3. 林业法律法规问答：https://github.com/17680329677/Forestry_LAW
4. 知识图谱学习（医药问答）：https://github.com/datawhalechina/team-learning-nlp/tree/master/KnowledgeGraph_Basic
5. 罪名判决根据卷宗预测：https://github.com/liuhuanyong/LawCrimeMining

##### 资源

1. 中文词向量：https://github.com/Embedding/Chinese-Word-Vectors
2. nlp资源库：https://github.com/fighting41love/funNLP
3. 中科院NLPAPI：https://nlp.datahorizon.cn/help.cgi.html
4. 法务nlp论文资源：https://github.com/bamtercelboo/Awesome-Law-NLP-Research-Work
5. 东南大学知识图谱研究生课程：https://github.com/npubird/KnowledgeGraphCourse
6. protegeweb:https://webprotege.stanford.edu/
7. 知识推理实践：https://www.cnblogs.com/xiaoqi/p/kg-inference-1.html
8. 知识图谱推理：http://reader.epubee.com/books/mobile/cc/cc219bda88f77cd8612c76540dd98cef/text00011.html
9. 知识图谱推理方法总结：https://zhuanlan.zhihu.com/p/78744231｜https://zhuanlan.zhihu.com/p/42340077｜https://my.oschina.net/u/4581664/blog/4376159
10. 华为知识图谱介绍：https://support.huaweicloud.com/usermanual-kg/kg_01_0004.html
11. 图数据库：https://github.com/arangodb/arangodb｜https://github.com/JanusGraph/janusgraph｜https://github.com/cayleygraph/cayley
12. 以知识为中心的情报智能：https://www.secrss.com/articles/14281

##### 可视化工具

参考：https://zhuanlan.zhihu.com/p/148990503

1. 社会关系可视化：https://github.com/gephi/gephi

   ![](http://www.designandanalytics.com/sites/default/files/finals-directed-low.png)

2. 图数据可视化与分析：https://github.com/antvis/graphin/![深度截图_选择区域_20210115213436](https://i.loli.net/2021/01/18/Kvk1G9DSJiAXfF6.png)

3. Ｇ６：https://github.com/antvis/G6

![](https://gw.alipayobjects.com/mdn/rms_f8c6a0/afts/img/A*PEFPSZwgqScAAAAAAAAAAABkARQnAQ)

#### 技术选型分析

仅列出不同点

##### 图数据库

| 数据库名称 | 特征                                                         |
| ---------- | ------------------------------------------------------------ |
| neo4j      | 社区版开源，使用广泛，python封装差                           |
| arangodb   | 开源，python封装完备，事务，可扩展，性能，提供文档/键值对储存模型，可以储存时间序列和GIS信息，机器学习原生支持 |
| JanusGraph | 开源，python封装完备，事务，可扩展，支持原生图谱分析推理     |

根据项目目标，我们需要储存与实体关系绑定的时空信息，建议选定arangodb作为知识图谱储存数据库

##### 图可视化

| 工具名称   | 特征                                                         |
| ---------- | ------------------------------------------------------------ |
| deepfinder | 闭源收费，安全领域产品                                       |
| graphin    | 开源，有时间序列分析功能，美观，有推理，具备图数据推理分析功能，基于Ｇ６，有本体编辑功能 |
| echarts    | 开源，美观                                                   |

根据项目目标，我们需要时空数据的呈现，着重图谱的知识分析推理功能，因此建议选定graphin作为图可视化工具

##### 本体编辑

| 工具名称 | 特征                                                         |
| -------- | ------------------------------------------------------------ |
| protege  | 开源                                                         |
| graphin  | 开源，有时间序列分析功能，美观，有推理，具备图数据推理分析功能，基于Ｇ６，有本体编辑功能 |

graphin已经集成了本体编辑功能且protege有一定学习成本，因此不建议使用protege

#### 科研计划

首先自己复现法律问答系统

然后再与团队讨论项目下一步计划