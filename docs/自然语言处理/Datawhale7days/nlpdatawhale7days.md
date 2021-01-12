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

