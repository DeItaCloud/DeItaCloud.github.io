# nlpdatawhale7days

## 序言

ＯＫ，这里随便写一些感想，首先就是好久没有写知识库了，我想以后要多写一些．学而不思则罔，写知识库也能督促我更好的学习．

第二个决定就是以后写的东西不会发到CSDN和简书中了，更不会上微博和微信，这种粪坑之中，markdown还是Ｔypora写的最棒，写完之后直接上知识库编译为网站．多则乱，给自己一个冥想进修地就好．

第三个想法在想，最近接触到一款很不错的CMS，叫做[Hugo](https://github.com/gohugoio/hugo)，也有一款很不错的主题叫做[Stack](https://github.com/CaiJimmy/hugo-theme-stack)，在考虑迁移过去，因为有评论系统，或者迁移到Gatsby的某个主题，但是好多之前的笔记都写着是mkdocs的语法，尤其是刑法笔记．



## 打卡0



这里开始正式打卡，学习知识图谱算是回到正轨上了，之前一直在学各种编程语言的基础，Py，Go，js，Ts，nim，相继学完，虽然没有非常深入，但是能稍微使用了（可能有两门语言笨拙一点），还是最喜欢py与Go，然后nim好期望它能发展的好．

知识图谱对我的老本行很有用，这次参与学习一个是了解入门知识图谱，目标是能够解决毕业论文的问题哈哈

第一天的内容在这里：https://github.com/datawhalechina/team-learning-nlp/blob/master/KnowledgeGraph_Basic/task01.md

哈哈今日是熟悉规则，配置运行环境，如下图，Neo4J的界面

![](https://s3.ax1x.com/2021/01/10/s16iVJ.png)

## 打卡１

第一日打卡，熟悉ｎｅｏ４ｊ的语法． Cypher查询语言



#### ＣＱＬ语言总结：

ＭＡＴＣＨ　查询

ＭＥＲＧＥ　创建关系

［］　关系

（）　实体

ｓｅｔ　修改值

ｒｅｍｏｖｅ　删除值

ｄｅｌｅｔｅ　删除实体



####  ｐｙｔｈｏｎ操作总结：

实体　ＮＯＤＥ

关系　ＲＥＬＡＴＩＯＮＳＨＩＰ



#### ＣＳＶ导入总结：



movies.csv

1. `movie:ID,name,:LABEL`
2. `tt0133093,The``Matrix,movie`
3. `tt0234215,The``Matrix``Reloaded,movie`
4. `tt0242653,The``Matrix``Revolutions,movie`



actors.csv

1. `person:ID,name,:LABEL`
2. `keanu,Keanu``Reeves,person`
3. `laurence,Laurence``Fishburne,person`
4. `carrieanne,Carrie-Anne``Moss,person`



roles.csv

1. `:START_ID,role,:END_ID`
2. `keanu,Neo,tt0133093`
3. `keanu,Neo,tt0234215`
4. `keanu,Neo,tt0242653`
5. `laurence,Morpheus,tt0133093`
6. `laurence,Morpheus,tt0234215`
7. `laurence,Morpheus,tt0242653`
8. `carrieanne,Trinity,tt0133093`



`./neo4j-admin import --database=new.db --nodes ../import/actors.csv --nodes ../import/movies.csv --relationships:ACTED_IN=../import/relas.csv`

导入成功：

```
Available resources:
  Total machine memory: 15.07GiB
  Free machine memory: 4.685GiB
  Max heap memory : 3.349GiB
  Processors: 16
  Configured max memory: 10.55GiB
  High-IO: true


Import starting 2021-01-11 20:36:05.891+0800
  Estimated number of nodes: 14.00 
  Estimated number of node properties: 34.00 
  Estimated number of relationships: 0.00 
  Estimated number of relationship properties: 0.00 
  Estimated disk space usage: 1.105KiB
  Estimated required memory usage: 1020MiB

(1/4) Node import 2021-01-11 20:36:05.902+0800
  Estimated number of nodes: 14.00 
  Estimated disk space usage: 1.105KiB
  Estimated required memory usage: 1020MiB
-......... .......... .......... .......... ..........   5% ∆90ms
.......... .......... .......... .......... ..........  10% ∆3ms
.......... .......... .......... .......... ..........  15% ∆1ms
.......... .......... .......... .......... ..........  20% ∆2ms
.......... .......... .......... .......... ..........  25% ∆1ms
.......... .......... .......... .......... ..........  30% ∆1ms
.......... .......... .......... .......... ..........  35% ∆1ms
.......... .......... .......... .......... ..........  40% ∆1ms
.......... .......... .......... .......... ..........  45% ∆0ms
.......... .......... .......... .......... ..........  50% ∆0ms
.......... .......... .......... .......... ..........  55% ∆1ms
.......... .......... .......... .......... ..........  60% ∆0ms
.......... .......... .......... .......... ..........  65% ∆0ms
.......... .......... .......... .......... ..........  70% ∆0ms
.......... .......... .......... .......... ..........  75% ∆1ms
.......... .......... .......... .......... ..........  80% ∆0ms
.......... .......... .......... .......... ..........  85% ∆0ms
.......... .......... .......... .......... ..........  90% ∆0ms
.......... .......... .......... .......... ..........  95% ∆0ms
.......... .......... .......... .......... .........(2/4) Relationship import 2021-01-11 20:36:06.081+0800
  Estimated number of relationships: 0.00 
  Estimated disk space usage: 0B
  Estimated required memory usage: 1.004GiB
(3/4) Relationship linking 2021-01-11 20:36:06.122+0800
  Estimated required memory usage: 1020MiB
(4/4) Post processing 2021-01-11 20:36:06.304+0800
  Estimated required memory usage: 1020MiB
-......... .......... .......... .......... ..........   5% ∆165ms
.......... .......... .......... .......... ..........  10% ∆0ms
.......... .......... .......... .......... ..........  15% ∆1ms
.......... .......... .......... .......... ..........  20% ∆1ms
.......... .......... .......... .......... ..........  25% ∆0ms
.......... .......... .......... .......... ..........  30% ∆0ms
.......... .......... .......... .......... ..........  35% ∆1ms
.......... .......... .......... .......... ..........  40% ∆0ms
.......... .......... .......... .......... ..........  45% ∆0ms
.......... .......... .......... .......... ..........  50% ∆0ms
.......... .......... .......... .......... ..........  55% ∆0ms
.......... .......... .......... .......... ..........  60% ∆1ms
.......... .......... .......... .......... ..........  65% ∆0ms
.......... .......... .......... .......... ..........  70% ∆1ms
.......... .......... .......... .......... ..........  75% ∆0ms
.......... .......... .......... .......... ..........  80% ∆0ms
.......... .......... .......... .......... ..........  85% ∆1ms
.......... .......... .......... .......... ..........  90% ∆0ms
.......... .......... .......... .......... ..........  95% ∆0ms
.......... .......... .......... .......... .........
IMPORT DONE in 851ms. 
Imported:
  14 nodes
  0 relationships
  34 properties
Peak memory usage: 1.004GiB

```

## 打卡２

clone from this repo:https://github.com/zhihao-chen/QASystemOnMedicalGraph

今天启动医药问答系统，有点小激动，在部署过程中遇到的坑：

1. 文件夹名称data -> DATA

2. 协议名称http -> bolt

3. sklearn版本0.20.4

   部署成功：

   ![](https://s3.ax1x.com/2021/01/12/sJaC5t.md.png)

## 打卡３

> 文章编写人：芙蕖<br/>
> github 地址：<br/>
> 特别鸣谢：[QASystemOnMedicalGraph](https://github.com/zhihao-chen/QASystemOnMedicalGraph)

### 一、引言

在计算机科学中，图形作为一种特定的数据结构，用于表达数据之间的复杂关系，如社交关系、组织架构、交通信息、网络拓扑等等。在图计算中，基本的数据结构表达式是：G=(V,E)，V=vertex(节点)，E=edge(边)。图形结构的数据结构一般以节点和边来表现，也可以在节点上增加键值对属性。图数据库是 NoSQL（非关系型数据库）的一种，它应用图形数据结构的特点（节点、属性和边）存储数据实体和相互之间的关系信息。

Neo4j 是当前较为主流和先进的原生图数据库之一，提供原生的图数据存储、检索和处理。它由 Neo Technology支持，从 2003 年开始开发，1.0 版本发布于 2010 年，2.0版本发布于 2013 年。经过十多年的发展，Neo4j 获得越来越高的关注度，它已经从一个 Java 领域内的图数据库逐渐发展成为适应多语言多框架的图数据库。Neo4j 支持ACID、集群、备份和故障转移，具有较高的可用性和稳定性；它具备非常好的直观性，通过图形化的界面表示节点和关系；同时它具备较高的可扩展性，能够承载上亿的节点、关系和属性，通过 REST 接口或者面向对象的 JAVA API进行访问。

### 二、Neo4j简介

#### 2.1 基本概念

Neo4j使用图相关的概念来描述数据模型，把数据保存为图中的节点以及节点之间的关系。数据主要由三部分构成：

- 节点。节点表示对象实例，每个节点有唯一的ID区别其它节点，节点带有属性；
- 关系。就是图里面的边，连接两个节点，另外这里的关系是有向的并带有属性；
- 属性。key-value对，存在于节点和关系中，如图1所示。

![图片.png](https://i.loli.net/2020/11/28/OGTbAcSw7UMdzHl.png)
> 图 1 节点、关系和属性三者的关系

#### 2.2 索引

- 动机：Neo4j使用遍历操作进行查询。为了加速查询，Neo4j会建立索引，并根据索引找到遍历用的起始节点；
- 介绍：默认情况下，相关的索引是由Apache Lucene提供的。但也能使用其他索引实现来提供。
- 操作：用户可以创建任意数量的命名索引。每个索引控制节点或者关系，而每个索引都通过key/value/object三个参数来工作。其中object要么是一个节点，要么是一个关系，取决于索引类型。另外，Neo4j中有关于节点（关系）的索引，系统通过索引实现从属性到节点（关系）的映射。
- 作用：
  - 查找操作：系统通过设定访问条件比如，遍历的方向，使用深度优先或广度优先算法等条件对图进行遍历，从一个节点沿着关系到其他节点；
  - 删除操作：Neo4j可以快速的插入删除节点和关系，并更新节点和关系中的属性。

#### 2.3 Neo4j的优势

那么，如此引人入胜的 Neo4j，与其他数据库相比，具有哪些明显的优势呢?这可以从以下几个方面来分析，主要表现为查询的高性能、设计的灵活性和开发的敏捷性等。

- **查询的高性能**

Neo4j是一个原生的图数据库引擎，它存储了原生的图数据，因此，可以使用图结构的自然伸展特性来设计免索引邻近节点遍历的查询算法，即图的遍历算法设计。图的遍历是图数据结构所具有的独特算法，即从一个节点开始，根据其连接的关系，可以快速和方便地找出它的邻近节点。这种查找数据的方法并不受数据量的大小所影响，因为邻近查询查找的始终是有限的局部数据，而不会对整个数据库进行搜索。所以，Neo4j具有非常高效的查询性能，相比于RDBMS，它的查询速度可以提高数倍乃至数十倍.而且查询速度不会因数据量的增长而下降，即数据库可以经久耐用，并且始终保持最初的活力。不像RDBMS那样，因为不可避免地使用了一些范式设计，所以在查询时如果需要表示一些复杂的关系，势必会构造很多连接，从而形成很多复杂的运算。并且在查询中更加可怕的是还会涉及大量数据，这些数据大多与结果毫无关系，有的可能仅仅是通过ID查找它的名称而已，所以随着数据量的增长，即使查询一小部分数据，查询也会变得越来越慢，性能日趋下降，以至于让人无法忍受。

- **设计的灵活性**

在日新月异的互联网应用中，业务需求会随着时间和条件的改变而发生变化，这对于以往使用结构化数据的系统来说，往往很难适应这种变化的需要。图数据结构的自然伸展特性及其非结构化的数据格式，让 Neo4j的数据库设计可以具有很大的伸缩性和灵活性。因为随着需求的变化而增加的节点、关系及其属性并不会影响到原来数据的正常使用，所以使用Neo4j来设计数据库，可以更接近业务需求的变化，可以更快地赶上需求发展变化的脚步。
大多数使用关系型数据库的系统，为了应对快速变化的业务需求，往往需要采取推倒重来的方法重构整个应用系统。而这样做的成本是巨大的。使用Neo4j可以最大限度地避免这种情况发生。虽然有时候，也许是因为最初的设计考虑得太不周全，或者为了获得更好的表现力，数据库变更和迁移在所难免，但是使用Neo4j来做这项工作也是非常容易的，至少它没有模式结构定义方面的苦恼。

- **开发的敏捷性**

图数据库设计中的数据模型，从需求的讨论开始，到程序开发和实现，以及最终保存在数据库中的样子，直观明了，似乎没有什么变化，甚至可以说本来就是一模一样的。这说明，业务需求与系统设计之间可以拉近距离，需求和实现结果之间越来越接近。这不但降低了业务人员与设计人员之间的沟通成本，也使得开发更加容易迭代，并且非常适合使用敏捷开发方法。

Neo4j本身可伸缩的设计灵活性，以及直观明了的数据模型设计，以及其自身简单易用的特点等，所有这些优势都充分说明，使用Neo4j很适合以一种测试驱动的方法应用于系统设计和开发自始至终的过程之中，通过迭代来加深对需求的理解，并通过迭代来完善数据模型设计。

- **与其他数据库的比较**

在图数据库领域，除Neo4j外，还有其他如OrientDB、Giraph、AllegroGraph等各种图数据库。与所有这些图数据库相比，Neo4j的优势表现在以下两个方面。

(1)Neo4j是一个原生图计算引擎，它存储和使用的数据自始至终都是使用原生的图结构数据进行处理的，不像有些图数据库，只是在计算处理时使用了图数据库，而在存储时还将数据保存在关系型数据库中。

(2）Neo4j是一个开源的数据库，其开源的社区版吸引了众多第三方的使用和推如开源项目Spring Data Neo4j就是一个做得很不错的例子，同时也得到了更多开发者的拥趸和支持，聚集了丰富的可供交流和学习的资源与案例。这些支持、推广和大量的使用，反过来会很好地推动Neo4j的发展。

- **综合表现**

Neo4j 查询的高性能表现、易于使用的特性及其设计的灵活性和开发的敏捷性，以及坚如磐石般的事务管理特性，都充分说明了使用Neo4j是一个不错的选择。有关它的所有优点，总结起来，主要表现在以下几个方面。

1. 闪电般的读/写速度，无与伦比的高性能表现；
2. 非结构化数据存储方式，在数据库设计上具有很大的灵活性；
3. 能很好地适应需求变化，并适合使用敏捷开发方法；
4. 很容易使用，可以用嵌入式、服务器模式、分布式模式等方式来使用数据库；
5. 使用简单框图就可以设计数据模型，方便建模；
6. 图数据的结构特点可以提供更多更优秀的算法设计；
7. 完全支持ACID完整的事务管理特性；
8. 提供分布式高可用模式，可以支持大规模的数据增长；
9. 数据库安全可靠，可以实时备份数据，很方便恢复数据；
10. 图的数据结构直观而形象地表现了现实世界的应用场景。

### 2.4 环境部署

#### 2.4.1 运行环境

- python3.0及以上
- neo4j 3.5.0及以上
- jdk 1.8.0

#### 2.4.2 neo4j安装及使用

进官方网站：[https://neo4j.com/](https://neo4j.com/)下载neo4j桌面版或者community版本的，自行安装好。

运行neo4j前，需要安装jdk 1.8.0的版本。配置好环境后，在命令行中输入：**java -version**，查看是否安装成功。

![图片.png](https://i.loli.net/2020/11/28/4aR1sToSEnve6bL.png) 
> 图 2 Neo4j 启动

> 注：neo4j和jdk都需要配置环境变量！！！

测试neo4j是否安装成功，在命令行中输入：**neo4j.bat console**，如下图 3 所示：

![图片.png](https://i.loli.net/2020/11/28/4aR1sToSEnve6bL.png) 
> 图 3  测试neo4j是否安装成功

如图 4 所示，已经开启了neo4j数据库，配置成功后，可以在浏览器中使用[http://localhost:7474/browser/](http://localhost:7474/browser/)网址查看数据库，但是前提是得把桌面的应用程序关掉。

> 注：记住数据库的用户名和密码，一般默认的是：用户：neo4j, 密码：neo4j。

![图片.png](https://i.loli.net/2020/11/28/wtkmLaIjiWDlRh4.png)
> 图 4  Neo4j 可视化界面

> 注：首次登陆会提醒你修改密码！！！

### 三、Neo4j 数据导入

#### 3.1 数据集简介

- 数据源：39健康网。包括15项信息，其中7类实体，约3.7万实体，21万实体关系。

- 本次组队学习搭建的系统的知识图谱结构如下：

![知识图谱结构](https://i.loli.net/2020/11/28/TacFAJUnCWfuZXr.png)
> 图 5 知识图谱结构

- 知识图谱实体类型

![知识图谱实体类型](https://i.loli.net/2020/11/28/7zlp2Y9du3Mon1U.png)
> 图 6 知识图谱实体类型

- 知识图谱实体关系类型

![知识图谱实体关系类型](https://i.loli.net/2020/11/28/QI2tCpk3LuTfoca.png)
> 图 6 知识图谱实体关系类型

- 知识图谱疾病属性

![知识图谱疾病属性](https://i.loli.net/2020/11/28/y4repEsqd9bPkSl.png)
> 图 7 知识图谱疾病属性

- 基于特征词分类的方法来识别用户查询意图

![基于特征词分类的方法来识别用户查询意图](https://i.loli.net/2020/11/28/r1ugnS3CPBWfmGk.png)
> 图 8 基于特征词分类的方法来识别用户查询意图

#### 3.2 数据导入 

##### 3.2.1 Neo4j 账号密码设置

要将 数据 导入 Neo4j 图数据库，首先需要 进入 build_graph.py 类中，在 类 MedicalGraph 中 的加入 本地 Neo4j 图数据库 的 账号和密码；

```s
    class MedicalGraph:
        def __init__(self):
            ...
            self.graph = Graph("http://localhost:7474", username="neo4j", password="自己的")
            ...
```

##### 3.2.2 导入 数据

运行 以下命令：

```s
    python build_graph.py 
```

> 注：由于数据量比较大，所以该过程需要运行几个小时 


#### 3.3 知识图谱展示

运行介绍之后，打开浏览器进入网址：[http://localhost:7474/browser/](http://localhost:7474/browser/)，可以看到我们导入的数据的知识图谱，如下：




#### 3.4 主体类 MedicalGraph 介绍

```s
class MedicalGraph:
    def __init__(self):
        pass
    
    # 读取文件，获得实体，实体关系
    def read_file(self):
        psss
    # 创建节点
    def create_node(self, label, nodes):
        pass
    # 创建疾病节点的属性
    def create_diseases_nodes(self, disease_info):
        pass
    # 创建知识图谱实体
    def create_graphNodes(self):
        pass
    # 创建实体关系边
    def create_graphRels(self):
        pass
    # 创建实体关系边
    def create_relationship(self, start_node, end_node, edges, rel_type, rel_name):
        pass
```
#### 3.5 主体类 MedicalGraph 中关键代码讲解

- 获取数据路径

```s
    cur_dir = '/'.join(os.path.abspath(__file__).split('/')[:-1])
    self.data_path = os.path.join(cur_dir, 'DATA/disease.csv')
```

- 链接 Neo4j 图数据库

```s
    self.graph = Graph("http://localhost:7474", username="neo4j", password="自己设定的密码")
```

- 读取文件，获得实体，实体关系

这部分代码的核心就是读取 数据文件，并 获取实体和实体关系信息。

- 实体信息：
  - diseases 疾病
  - aliases  别名
  - symptoms  症状
  - parts  部位
  - departments  科室
  - complications 并发症
  - drugs  药品
- 实体关系：
  - disease_to_symptom  疾病与症状关系
  - disease_to_alias  疾病与别名关系
  - diseases_to_part  疾病与部位关系
  - disease_to_department  疾病与科室关系
  - disease_to_complication  疾病与并发症关系
  - disease_to_drug  疾病与药品关系
- disease 实体 属性信息：
  - name
  - age 年龄
  - infection 传染性
  - insurance  医保
  - checklist  检查项
  - treatment  治疗方法
  - period 治愈周期
  - rate  治愈率
  - money 费用

```s
    def read_file(self):
        """
        读取文件，获得实体，实体关系
        :return:
        """
        # cols = ["name", "alias", "part", "age", "infection", "insurance", "department", "checklist", "symptom",
        #         "complication", "treatment", "drug", "period", "rate", "money"]
        # 实体
        diseases = []  # 疾病
        aliases = []  # 别名
        symptoms = []  # 症状
        parts = []  # 部位
        departments = []  # 科室
        complications = []  # 并发症
        drugs = []  # 药品

        # 疾病的属性：age, infection, insurance, checklist, treatment, period, rate, money
        diseases_infos = []
        # 关系
        disease_to_symptom = []  # 疾病与症状关系
        disease_to_alias = []  # 疾病与别名关系
        diseases_to_part = []  # 疾病与部位关系
        disease_to_department = []  # 疾病与科室关系
        disease_to_complication = []  # 疾病与并发症关系
        disease_to_drug = []  # 疾病与药品关系

        all_data = pd.read_csv(self.data_path, encoding='gb18030').loc[:, :].values
        for data in all_data:
            disease_dict = {}  # 疾病信息
            # 疾病
            disease = str(data[0]).replace("...", " ").strip()
            disease_dict["name"] = disease
            # 别名
            line = re.sub("[，、；,.;]", " ", str(data[1])) if str(data[1]) else "未知"
            for alias in line.strip().split():
                aliases.append(alias)
                disease_to_alias.append([disease, alias])
            # 部位
            part_list = str(data[2]).strip().split() if str(data[2]) else "未知"
            for part in part_list:
                parts.append(part)
                diseases_to_part.append([disease, part])
            # 年龄
            age = str(data[3]).strip()
            disease_dict["age"] = age
            # 传染性
            infect = str(data[4]).strip()
            disease_dict["infection"] = infect
            # 医保
            insurance = str(data[5]).strip()
            disease_dict["insurance"] = insurance
            # 科室
            department_list = str(data[6]).strip().split()
            for department in department_list:
                departments.append(department)
                disease_to_department.append([disease, department])
            # 检查项
            check = str(data[7]).strip()
            disease_dict["checklist"] = check
            # 症状
            symptom_list = str(data[8]).replace("...", " ").strip().split()[:-1]
            for symptom in symptom_list:
                symptoms.append(symptom)
                disease_to_symptom.append([disease, symptom])
            # 并发症
            complication_list = str(data[9]).strip().split()[:-1] if str(data[9]) else "未知"
            for complication in complication_list:
                complications.append(complication)
                disease_to_complication.append([disease, complication])
            # 治疗方法
            treat = str(data[10]).strip()[:-4]
            disease_dict["treatment"] = treat
            # 药品
            drug_string = str(data[11]).replace("...", " ").strip()
            for drug in drug_string.split()[:-1]:
                drugs.append(drug)
                disease_to_drug.append([disease, drug])
            # 治愈周期
            period = str(data[12]).strip()
            disease_dict["period"] = period
            # 治愈率
            rate = str(data[13]).strip()
            disease_dict["rate"] = rate
            # 费用
            money = str(data[14]).strip() if str(data[14]) else "未知"
            disease_dict["money"] = money

            diseases_infos.append(disease_dict)

        return set(diseases), set(symptoms), set(aliases), set(parts), set(departments), set(complications), \
                set(drugs), disease_to_alias, disease_to_symptom, diseases_to_part, disease_to_department, \
                disease_to_complication, disease_to_drug, diseases_infos
```

- 创建节点

这部分代码主要是为了创建不包含属性的 节点

```s
    def create_node(self, label, nodes):
        """
        创建节点
        :param label: 标签
        :param nodes: 节点
        :return:
        """
        count = 0
        for node_name in nodes:
            node = Node(label, name=node_name)
            self.graph.create(node)
            count += 1
            print(count, len(nodes))
        return
```

- 创建带有属性节点

```s
    def create_diseases_nodes(self, disease_info):
        """
        创建疾病节点的属性
        :param disease_info: list(Dict)
        :return:
        """
        count = 0
        for disease_dict in disease_info:
            node = Node("Disease", name=disease_dict['name'], age=disease_dict['age'],
                        infection=disease_dict['infection'], insurance=disease_dict['insurance'],
                        treatment=disease_dict['treatment'], checklist=disease_dict['checklist'],
                        period=disease_dict['period'], rate=disease_dict['rate'],
                        money=disease_dict['money'])
            self.graph.create(node)
            count += 1
            print(count)
        return
```

- 创建知识图谱实体

```s
    def create_graphNodes(self):
        """
        创建知识图谱实体
        :return:
        """
        disease, symptom, alias, part, department, complication, drug, rel_alias, rel_symptom, rel_part, \
        rel_department, rel_complication, rel_drug, rel_infos = self.read_file()
        self.create_diseases_nodes(rel_infos)
        self.create_node("Symptom", symptom)
        self.create_node("Alias", alias)
        self.create_node("Part", part)
        self.create_node("Department", department)
        self.create_node("Complication", complication)
        self.create_node("Drug", drug)

        return
```

- 创建知识图谱关系

```s
    def create_graphRels(self):
        disease, symptom, alias, part, department, complication, drug, rel_alias, rel_symptom, rel_part, \
        rel_department, rel_complication, rel_drug, rel_infos = self.read_file()

        self.create_relationship("Disease", "Alias", rel_alias, "ALIAS_IS", "别名")
        self.create_relationship("Disease", "Symptom", rel_symptom, "HAS_SYMPTOM", "症状")
        self.create_relationship("Disease", "Part", rel_part, "PART_IS", "发病部位")
        self.create_relationship("Disease", "Department", rel_department, "DEPARTMENT_IS", "所属科室")
        self.create_relationship("Disease", "Complication", rel_complication, "HAS_COMPLICATION", "并发症")
        self.create_relationship("Disease", "Drug", rel_drug, "HAS_DRUG", "药品")
```

- 创建实体关系边

```s
    def create_relationship(self, start_node, end_node, edges, rel_type, rel_name):
        """
        创建实体关系边
        :param start_node:
        :param end_node:
        :param edges:
        :param rel_type:
        :param rel_name:
        :return:
        """
        count = 0
        # 去重处理
        set_edges = []
        for edge in edges:
            set_edges.append('###'.join(edge))
        all = len(set(set_edges))
        for edge in set(set_edges):
            edge = edge.split('###')
            p = edge[0]
            q = edge[1]
            query = "match(p:%s),(q:%s) where p.name='%s'and q.name='%s' create (p)-[rel:%s{name:'%s'}]->(q)" % (
                start_node, end_node, p, q, rel_type, rel_name)
            try:
                self.graph.run(query)
                count += 1
                print(rel_type, count, all)
            except Exception as e:
                print(e)
        return
```



### 四、总结 

Neo4j是一个高性能的,NOSQL图形数据库，它将结构化数据存储在网络上而不是表中。Neo4j也可以被看作是一个高性能的图引擎，该引擎具有成熟数据库的所有特性。Neo4j是一个高度可扩展的本机图形数据库，旨在专门利用数据和数据关系。使用Neo4j，开发人员可以构建智能应用程序，以实时遍历当今大型的，相互关联的数据集。大家工作在一个面向对象的、灵活的网络结构下而不是严格、静态的表中，但是可以享受到具备完全的事务特性、企业级的数据库的所有好处。

Neo4j因其嵌入式、高性能、轻量级等优势，越来越受到关注。

### 参考资料 

1. [QASystemOnMedicalGraph](https://github.com/zhihao-chen/QASystemOnMedicalGraph)
2. [韩浩明.图数据库系统研究综述[J].计算机光盘软件与应用,2014,17(23):14-15.](http://gb.oversea.cnki.net/KCMS/detail/detail.aspx?filename=GPRJ201423018&dbcode=CJFD&dbname=CJFD2014) 



## 打卡４


> 文章编写人：王翔<br/>
> github 地址：<br/>
> 特别鸣谢：[QASystemOnMedicalGraph](https://github.com/zhihao-chen/QASystemOnMedicalGraph)


### 一、引言

本部分任务主要是**将用户输入问答系统的自然语言转化成知识库的查询语句**，因此本文将分成两部分进行介绍。
- 第一部分介绍任务所涉及的背景知识;
- 第二部分则是相应的代码和其注释


### 二、什么是问答系统？

#### 2.1 问答系统简介

问答系统(Question Answering System，QA System)是用来回答人提出的自然语言问题的系统。根据划分标准不同，问答系统可以被分为各种不同的类型。

* 问答系统从知识领域划分：
  * 封闭领域：封闭领域系统专注于回答特定领域的问题，由于问题领域受限，系统有比较大的发挥空间，可以导入领域知识或将答案来源全部转换成结构性资料来有效提升系统的表现；
  * 开放领域：开放领域系统则希望不设限问题的内容范围，因此其难度也相对较大。

* 问答系统从实现方式划分：
  * 基于流水线（pipeline）实现：如下图 1 所示，基于流水线实现的问答系统有四大核心模块，分别由自然语言理解（NLU）、对话状态跟踪器（DST）、对话策略（DPL）和自然语言生成（NLG）依次串联构成的一条流水线，各模块可独立设计，模块间协作完成任务。
  * 基于端到端（end-to-end）实现：基于端到端实现的问答系统，主要是结合深度学习技术，通过海量数据训练，挖掘出从用户自然语言输入到系统自然语言输出的整体映射关系，而忽略中间过程的一种方法。但就目前工业界整体应用而言，工业界的问答系统目前大多采用的还是基于流水线实现的方式。

![](https://upload-images.jianshu.io/upload_images/10798244-16aa357b7be5a646.png?imageMogr2/auto-orient/strip|imageView2/2/w/816/format/webp)
> 图 1 基于流水线（pipeline）实现

* 问答系统从答案来源划分：
  * 「知识库问答」。是目前的研究热点。知识库问答（knowledge base question answering, KB-QA）即给定自然语言问题，通过对问题进行语义理解和解析，进而利用知识库进行查询、推理得出答案。如下图 2 所示：
  * 「常问问题问答」；
  * 「新闻问答」；
  * 「网际网路问答」；

![](https://upload-images.jianshu.io/upload_images/10798244-afb41aa23fee13c7.png?imageMogr2/auto-orient/strip|imageView2/2/w/1240)
> 图 2 知识库问答

#### 2.2 Query理解

##### 2.2.1  Query理解介绍

Query理解 (QU，Query Understanding)，简单来说就是从词法、句法、语义三个层面对 Query 进行结构化解析。

- 搜索 Query 理解包含的模块主要有：
  - Query预处理
  - Query纠错
  - Query扩展
  - Query归一
  - 意图识别
  - 槽值填充
  - Term重要性分析；
  - ...

由于本任务后面代码主要涉及意图识别和槽位解析，因此这里仅对这两部分内容做介绍：

##### 2.2.2 意图识别

- 介绍：意图识别是用来检测用户当前输入的意图，通常其被建模为将一段自然语言文本分类为预先设定的一个或多个意图的文本分类任务。
- 所用方法：和文本分类模型的方法大同小异，主要有：
  - 基于词典模板的规则分类
  - 传统的机器学习模型（文本特征工程+分类器）
  - 深度学习模型（Fasttext、TextCNN、BiLSTM + Self-Attention、BERT等）

![](https://upload-images.jianshu.io/upload_images/10798244-467c5be884303091.png?imageMogr2/auto-orient/strip|imageView2/2/w/1240)
> 图 3 意图识别

##### 2.2.3 槽值填充

- 介绍：槽值填充就是根据我们既定的一些结构化字段，将用户输入的信息中与其对应的部分提取出来。因此，槽值填充经常被建模为序列标注的任务。
- 举例介绍：例如下图所示的 Query "北京飞成都的机票"，通过意图分类模型可以识别出 Query 的整体意图是订机票，在此基础上进一步语义解析出对应的出发地 Depart="北京"，到达地 Arrive="成都"，所以生成的形式化表达可以是：Ticket=Order(Depart,Arrive)，Depart={北京}，Arrive={成都}。

![](https://upload-images.jianshu.io/upload_images/10798244-25aa5d0560dfee1a.jpg?imageMogr2/auto-orient/strip|imageView2/2/w/1240)
> 图 4 槽值填充

- 序列标注的任务常用的模型有：【注：这部分内容，第二期知识图谱组队学习将进行介绍】
  - 词典匹配；
  - BiLSTM + CRF；
  - IDCNN
  - BERT等。

### 三、任务实践

![](https://upload-images.jianshu.io/upload_images/10798244-322785573485895d.png?imageMogr2/auto-orient/strip|imageView2/2/w/1240)
> 图 5 基于知识图谱的问答系统框架

#### 四、 主体类 EntityExtractor 框架介绍

```s
#!/usr/bin/env python3
# coding: utf-8
import os
import ahocorasick
from sklearn.externals import joblib
import jieba
import numpy as np

class EntityExtractor:
    def __init__(self):
        pass

    # 构造actree，加速过滤
    def build_actree(self, wordlist):
        """
        构造actree，加速过滤
        :param wordlist:
        :return:
        """
        pass
    # 模式匹配, 得到匹配的词和类型。如疾病，疾病别名，并发症，症状
    def entity_reg(self, question):
        """
        模式匹配, 得到匹配的词和类型。如疾病，疾病别名，并发症，症状
        :param question:str
        :return:
        """
        pass

    # 当全匹配失败时，就采用相似度计算来找相似的词
    def find_sim_words(self, question):
        """
        当全匹配失败时，就采用相似度计算来找相似的词
        :param question:
        :return:
        """
        pass

    # 采用DP方法计算编辑距离
    def editDistanceDP(self, s1, s2):
        """
        采用DP方法计算编辑距离
        :param s1:
        :param s2:
        :return:
        """
        pass

    # 计算词语和字典中的词的相似度
    def simCal(self, word, entities, flag):
        """
        计算词语和字典中的词的相似度
        相同字符的个数/min(|A|,|B|)   +  余弦相似度
        :param word: str
        :param entities:List
        :return:
        """
        pass

    # 基于特征词分类
    def check_words(self, wds, sent):
        """
        基于特征词分类
        :param wds:
        :param sent:
        :return:
        """
        pass

    # 提取问题的TF-IDF特征
    def tfidf_features(self, text, vectorizer):
        """
        提取问题的TF-IDF特征
        :param text:
        :param vectorizer:
        :return:
        """
        pass

    # 提取问题的关键词特征
    def other_features(self, text):
        """
        提取问题的关键词特征
        :param text:
        :return:
        """
        pass

    # 预测意图
    def model_predict(self, x, model):
        """
        预测意图
        :param x:
        :param model:
        :return:
        """
        pass

    # 实体抽取主函数
    def extractor(self, question):
        pass
```


### 五、命名实体识别任务实践

#### 5.1 命名实体识别整体思路介绍

- step 1：对于用户的输入，先使用预先构建的疾病、疾病别名、并发症和症状的AC Tree进行匹配；
- step 2：若全都无法匹配到相应实体，则使用结巴切词库对用户输入的文本进行切分；
- step 3：然后将每一个词都去与疾病词库、疾病别名词库、并发症词库和症状词库中的词计算相似度得分（overlap score、余弦相似度分数和编辑距离分数），如果相似度得分超过0.7，则认为该词是这一类实体；
- step 4：最后排序选取最相关的词作为实体（项目所有的实体类型如下图所示，但实体识别时仅使用了疾病、别名、并发症和症状四种实体）

![](https://upload-images.jianshu.io/upload_images/10798244-b593dcc06d95bb35.png?imageMogr2/auto-orient/strip|imageView2/2/w/1240)
> 图 6 实体介绍

本部分所有的代码都来自 entity_extractor.py 中的 EntityExtractor 类，为了方便讲解，对类内的内容进行重新组织注释


#### 5.2 结合代码介绍

##### 5.2.1 构建 AC Tree

先通过 entity_extractor.py 中 类 EntityExtractor 的 build_actree 函数构建AC Tree

- 函数模块
```s
    def build_actree(self, wordlist):
        """
        构造actree，加速过滤
        :param wordlist:
        :return:
        """
        actree = ahocorasick.Automaton()
        # 向树中添加单词
        for index, word in enumerate(wordlist):
            actree.add_word(word, (index, word))
        actree.make_automaton()
        return actree
```

- 函数调用模块
```s
    def __init__(self):
        ...
        self.disease_path = cur_dir + 'disease_vocab.txt'
        self.symptom_path = cur_dir + 'symptom_vocab.txt'
        self.alias_path = cur_dir + 'alias_vocab.txt'
        self.complication_path = cur_dir + 'complications_vocab.txt'

        self.disease_entities = [w.strip() for w in open(self.disease_path, encoding='utf8') if w.strip()]
        self.symptom_entities = [w.strip() for w in open(self.symptom_path, encoding='utf8') if w.strip()]
        self.alias_entities = [w.strip() for w in open(self.alias_path, encoding='utf8') if w.strip()]
        self.complication_entities = [w.strip() for w in open(self.complication_path, encoding='utf8') if w.strip()]

        self.region_words = list(set(self.disease_entities+self.alias_entities+self.symptom_entities))

        # 构造领域actree
        self.disease_tree = self.build_actree(list(set(self.disease_entities)))
        self.alias_tree = self.build_actree(list(set(self.alias_entities)))
        self.symptom_tree = self.build_actree(list(set(self.symptom_entities)))
        self.complication_tree = self.build_actree(list(set(self.complication_entities)))
        ...
```

##### 5.2.2 使用AC Tree进行问句过滤

- 函数模块
```s
    def entity_reg(self, question):
        """
        模式匹配, 得到匹配的词和类型。如疾病，疾病别名，并发症，症状
        :param question:str
        :return:
        """
        self.result = {}

        for i in self.disease_tree.iter(question):
            word = i[1][1]
            if "Disease" not in self.result:
                self.result["Disease"] = [word]
            else:
                self.result["Disease"].append(word)

        for i in self.alias_tree.iter(question):
            word = i[1][1]
            if "Alias" not in self.result:
                self.result["Alias"] = [word]
            else:
                self.result["Alias"].append(word)

        for i in self.symptom_tree.iter(question):
            wd = i[1][1]
            if "Symptom" not in self.result:
                self.result["Symptom"] = [wd]
            else:
                self.result["Symptom"].append(wd)

        for i in self.complication_tree.iter(question):
            wd = i[1][1]
            if "Complication" not in self.result:
                self.result["Complication"] = [wd]
            else:
                self.result["Complication"] .append(wd)

        return self.result
```
- 函数调用模块
```s
    def extractor(self, question):
        self.entity_reg(question)
        ...
```

##### 5.2.3 使用 相似度进行实体匹配

当AC Tree的匹配都没有匹配到实体时，使用查找相似词的方式进行实体匹配

```s
def find_sim_words(self, question):
    """
    当全匹配失败时，就采用相似度计算来找相似的词
    :param question:
    :return:
    """
    import re
    import string
    from gensim.models import KeyedVectors
    
    # 使用结巴加载自定义词典
    jieba.load_userdict(self.vocab_path)
    # 加载词向量
    self.model = KeyedVectors.load_word2vec_format(self.word2vec_path, binary=False)
    
    # 数据预处理，正则去除特殊符号
    sentence = re.sub("[{}]", re.escape(string.punctuation), question)
    sentence = re.sub("[，。‘’；：？、！【】]", " ", sentence)
    sentence = sentence.strip()
    
    # 使用结巴进行分词
    words = [w.strip() for w in jieba.cut(sentence) if w.strip() not in self.stopwords and len(w.strip()) >= 2]

    alist = []
    
    # 对每个词，都让其与每类实体词典进行相似对比，
    # 最终选取分数最高的实体和其属于的实体类型
    for word in words:
        temp = [self.disease_entities, self.alias_entities, self.symptom_entities, self.complication_entities]
        for i in range(len(temp)):
            flag = ''
            if i == 0:
                flag = "Disease"
            elif i == 1:
                flag = "Alias"
            elif i == 2:
                flag = "Symptom"
            else:
                flag = "Complication"
            scores = self.simCal(word, temp[i], flag)
            alist.extend(scores)
    temp1 = sorted(alist, key=lambda k: k[1], reverse=True)
    if temp1:
        self.result[temp1[0][2]] = [temp1[0][0]]

# 计算词语和字典中的词的相似度
def simCal(self, word, entities, flag):
    """
    计算词语和字典中的词的相似度
    相同字符的个数/min(|A|,|B|)   +  余弦相似度
    :param word: str
    :param entities:List
    :return:
    """
    a = len(word)
    scores = []
    for entity in entities:
        sim_num = 0
        b = len(entity)
        c = len(set(entity+word))
        temp = []
        for w in word:
            if w in entity:
                sim_num += 1
        if sim_num != 0:
            score1 = sim_num / c  # overlap score
            temp.append(score1)
        try:
            score2 = self.model.similarity(word, entity)  # 余弦相似度分数
            temp.append(score2)
        except:
            pass
        score3 = 1 - self.editDistanceDP(word, entity) / (a + b)  # 编辑距离分数
        if score3:
            temp.append(score3)

        score = sum(temp) / len(temp)
        if score >= 0.7:
            scores.append((entity, score, flag))

    scores.sort(key=lambda k: k[1], reverse=True)
    return scores

```

### 六、意图识别任务实践

#### 6.1 意图识别整体思路介绍

- step 1：利用TF-IDF表征文本特征，同时构建一些人工特征（每一类意图常见词在句子中出现的个数）；
- step 2：训练朴素贝叶斯模型进行意图识别任务；
- step 3：使用实体信息进行意图的纠正和补充。

![](https://upload-images.jianshu.io/upload_images/10798244-6113c647b881e4aa.png?imageMogr2/auto-orient/strip|imageView2/2/w/1240)
> 图 7 意图识别整体举例介绍

该项目通过手工标记210条意图分类训练数据，并采用朴素贝叶斯算法训练得到意图分类模型。其最佳测试效果的F1值达到了96.68%。

#### 6.2 意图识别整体思路介绍

##### 6.2.1 特征构建

1. TF-IDF特征
```s
# 提取问题的TF-IDF特征
def tfidf_features(self, text, vectorizer):
    """
    提取问题的TF-IDF特征
    :param text:
    :param vectorizer:
    :return:
    """
    jieba.load_userdict(self.vocab_path)
    words = [w.strip() for w in jieba.cut(text) if w.strip() and w.strip() not in self.stopwords]
    sents = [' '.join(words)]

    tfidf = vectorizer.transform(sents).toarray()
    return tfidf
```
2. 人工特征
```s	    
self.symptom_qwds = ['什么症状', '哪些症状', '症状有哪些', '症状是什么', '什么表征', '哪些表征', '表征是什么',
                     '什么现象', '哪些现象', '现象有哪些', '症候', '什么表现', '哪些表现', '表现有哪些',
                     '什么行为', '哪些行为', '行为有哪些', '什么状况', '哪些状况', '状况有哪些', '现象是什么',
                     '表现是什么', '行为是什么']  # 询问症状
self.cureway_qwds = ['药', '药品', '用药', '胶囊', '口服液', '炎片', '吃什么药', '用什么药', '怎么办',
                     '买什么药', '怎么治疗', '如何医治', '怎么医治', '怎么治', '怎么医', '如何治',
                     '医治方式', '疗法', '咋治', '咋办', '咋治', '治疗方法']  # 询问治疗方法
self.lasttime_qwds = ['周期', '多久', '多长时间', '多少时间', '几天', '几年', '多少天', '多少小时',
                      '几个小时', '多少年', '多久能好', '痊愈', '康复']  # 询问治疗周期
self.cureprob_qwds = ['多大概率能治好', '多大几率能治好', '治好希望大么', '几率', '几成', '比例',
                      '可能性', '能治', '可治', '可以治', '可以医', '能治好吗', '可以治好吗', '会好吗',
                      '能好吗', '治愈吗']  # 询问治愈率
self.check_qwds = ['检查什么', '检查项目', '哪些检查', '什么检查', '检查哪些', '项目', '检测什么',
                   '哪些检测', '检测哪些', '化验什么', '哪些化验', '化验哪些', '哪些体检', '怎么查找',
                   '如何查找', '怎么检查', '如何检查', '怎么检测', '如何检测']  # 询问检查项目
self.belong_qwds = ['属于什么科', '什么科', '科室', '挂什么', '挂哪个', '哪个科', '哪些科']  # 询问科室
self.disase_qwds = ['什么病', '啥病', '得了什么', '得了哪种', '怎么回事', '咋回事', '回事',
                    '什么情况', '什么问题', '什么毛病', '啥毛病', '哪种病']  # 询问疾病
 
def other_features(self, text):
	"""
	提取问题的关键词特征
	:param text:
	:return:
	"""
	features = [0] * 7
	for d in self.disase_qwds:
	    if d in text:
	        features[0] += 1
	
	for s in self.symptom_qwds:
	    if s in text:
	        features[1] += 1
	
	for c in self.cureway_qwds:
	    if c in text:
	        features[2] += 1
	
	for c in self.check_qwds:
	    if c in text:
	        features[3] += 1
	for p in self.lasttime_qwds:
	    if p in text:
	        features[4] += 1
	
	for r in self.cureprob_qwds:
	    if r in text:
	        features[5] += 1
	
	for d in self.belong_qwds:
	    if d in text:
	        features[6] += 1
	
	m = max(features)
	n = min(features)
	normed_features = []
	if m == n:
	    normed_features = features
	else:
	    for i in features:
	        j = (i - n) / (m - n)
	        normed_features.append(j)
	
	return np.array(normed_features)

```

##### 6.2.2 使用朴素贝叶斯进行文本分类
- 项目没有给出训练过程，可参考下面sklearn的例子
```s
    # 项目没有给出训练过程，可参考下面sklearn的例子
    from sklearn.naive_bayes import MultinomialNB 

    mnb = MultinomialNB()   
    mnb.fit(X_train,y_train)   
    y_predict = mnb.predict(X_test)

    # 意图分类模型文件
    self.tfidf_path = os.path.join(cur_dir, 'model/tfidf_model.m')
    self.nb_path = os.path.join(cur_dir, 'model/intent_reg_model.m')  #朴素贝叶斯模型
    self.tfidf_model = joblib.load(self.tfidf_path)
    self.nb_model = joblib.load(self.nb_path)

    # 意图预测
    tfidf_feature = self.tfidf_features(question, self.tfidf_model)

    other_feature = self.other_features(question)
    m = other_feature.shape
    other_feature = np.reshape(other_feature, (1, m[0]))
    feature = np.concatenate((tfidf_feature, other_feature), axis=1)
    predicted = self.model_predict(feature, self.nb_model)
    intentions.append(predicted[0])
```

- 根据所识别的实体进行补充和纠正意图
```s
# 已知疾病，查询症状
if self.check_words(self.symptom_qwds, question) and ('Disease' in types or 'Alia' in types):
    intention = "query_symptom"
    if intention not in intentions:
        intentions.append(intention)
# 已知疾病或症状，查询治疗方法
if self.check_words(self.cureway_qwds, question) and \
        ('Disease' in types or 'Symptom' in types or 'Alias' in types or 'Complication' in types):
    intention = "query_cureway"
    if intention not in intentions:
        intentions.append(intention)
# 已知疾病或症状，查询治疗周期
if self.check_words(self.lasttime_qwds, question) and ('Disease' in types or 'Alia' in types):
    intention = "query_period"
    if intention not in intentions:
        intentions.append(intention)
# 已知疾病，查询治愈率
if self.check_words(self.cureprob_qwds, question) and ('Disease' in types or 'Alias' in types):
    intention = "query_rate"
    if intention not in intentions:
        intentions.append(intention)
# 已知疾病，查询检查项目
if self.check_words(self.check_qwds, question) and ('Disease' in types or 'Alias' in types):
    intention = "query_checklist"
    if intention not in intentions:
        intentions.append(intention)
# 查询科室
if self.check_words(self.belong_qwds, question) and \
        ('Disease' in types or 'Symptom' in types or 'Alias' in types or 'Complication' in types):
    intention = "query_department"
    if intention not in intentions:
        intentions.append(intention)
# 已知症状，查询疾病
if self.check_words(self.disase_qwds, question) and ("Symptom" in types or "Complication" in types):
    intention = "query_disease"
    if intention not in intentions:
        intentions.append(intention)

# 若没有检测到意图，且已知疾病，则返回疾病的描述
if not intentions and ('Disease' in types or 'Alias' in types):
    intention = "disease_describe"
    if intention not in intentions:
        intentions.append(intention)
# 若是疾病和症状同时出现，且出现了查询疾病的特征词，则意图为查询疾病
if self.check_words(self.disase_qwds, question) and ('Disease' in types or 'Alias' in types) \
        and ("Symptom" in types or "Complication" in types):
    intention = "query_disease"
    if intention not in intentions:
        intentions.append(intention)
# 若没有识别出实体或意图则调用其它方法
if not intentions or not types:
    intention = "QA_matching"
    if intention not in intentions:
        intentions.append(intention)

self.result["intentions"] = intentions

```

后续就是通过上述得到的意图信息和实体信息选择对应的模版，并将实体信息填充入组成查询语句进行数据库查询。

### 参考资料 

1. [ QASystemOnMedicalGraph](https://github.com/zhihao-chen/QASystemOnMedicalGraph)

## 打卡５

教程链接：https://github.com/datawhalechina/team-learning-nlp/blob/master/KnowledgeGraph_Basic/task05.md

## 总结

这次的打卡学习让我认识到了建立知识问答系统的流程和实现，熟悉neo4j和命名实体识别｜意图识别的功能和任务，接下来我还需要学习，如何建立知识图谱，还有如何利用知识图谱进行知识推理．附上资料集链接：https://deitacloud.github.io/site/%E8%87%AA%E7%84%B6%E8%AF%AD%E8%A8%80%E5%A4%84%E7%90%86/note/