# R语言特征
1. 对大小写敏感
2. 通常，数字，字母，. 和 _都是允许的(在一些国家还包括重音字母)。不过，一个命名必须以 . 或者字母开头，并且如果以 . 开头，第二个字符不允许是数字。
3. 基本命令要么是表达式（expressions）要么就是 赋值（assignments）。
4. 命令可以被 (;)隔开，或者另起一行。
5. 基本命令可以通过大括弧({和}) 放在一起构成一个复合表达式（compound expression）。
6. 一行中，从井号(#)开始到句子收尾之间的语句就是是注释。
7. R是动态类型、强类型的语言。
8. R的基本数据类型有数值型（numeric）、字符型（character）、复数型（complex）和逻辑型（logical），对象类型有向量、因子、数组、矩阵、数据框、列表、时间序列。

# 基础指令

## 运行
q()——退出R程序   
tab——自动补全   
ctrl+L——清空console   
ESC——中断当前计算   

## 输入输出（读入输出数据、文件）
assign("x",c(1,2,3)) 和 x <- c(1,2,3) 和 c(1,2,3)->x ——向量赋值
 
read.table（"infantry.txt", sep="\t"， header=TRUE）——seq属性用其它字符分割，比如文本文件用空格（tab）分隔，header设置为文件中已经存在表头名称

read.csv("targets.csv")——读入csv（Comma Seperated Values）文件，属性被逗号分割

read.csv(url("<link>"))——read.csv() 和 url()的合体，读存在网上的数据

write.table(Data, file="file.txt", row.names = FALSE, quote=FALSE)——输出，quote为FALSE去掉字符串类型的双引号，write.table(stasum, "stasum.csv",row.names = FALSE,col.name=FALSE,sep=",",append=TRUE)

write.csv（data，file="foo.csv",row.names=FALSE）——写成csv格式,row.names=FALSE去掉行号
 
print（）——打印

# 数据查看
## 数据结构
R是一种基于对象（Object）的语言，对象具有很多属性（Attribute），其中一种重要的属性就是类（Class），最基本的类包括了数值（numeric）、逻辑（logical）、字符（character）、列表（list），符合类包括矩阵（matrix）、数组（array）、因子（factor）、数据框（dataframe）。

##　绘图
plot()——绘制图像


barplot(<vector>)——绘制柱状图，vector可增加名称。也可以绘制直方图，和hist（）均分数据不太一样，需要用table（）统计各个子分段下样本数量后在画图。

boxplot（）——箱图，研究变量的中心趋势，以及变量发散情况和离群值。上体顶部和底部为上下四分位数，中间粗线为中位数，上下伸出的垂直部分为数据的散步范围，最远点为1.5倍四分为点，超出后为异常点，用圆圈表示。boxplot(y~f,notch=TRUE,col=1:3,add=TRUE)#y是数据，f是由因子构成，notch是带有切口的箱型图，add=T图叠加到上一幅图。

plot（f，y）——箱线图，f是因子，y是与f因子对应的数值

## 控制
 
a<-c()——向量初始化

vector <- numeric（<int>）——创建初始向量<int>个数，并赋初值为0

length（vector）<- leg——修改对象长度为leg

names(vector) <- c("A","B","C")——给向量起名称
 
vector["A"]——通过名称访问对应元素

 a == c(1, 99, 3)——比较每一个元素对应是否相等

c（0，1）——创建向量，向量内元素类型应一致！

seq（5，9）和 5：9 ——连续向量，等差数列

seq（5，9，0.5）——以0.5为间隔创建

seq(from,to,length,by)

## 矩阵
array（data=NA,dim=length(data),dimnames=null）——数组、矩阵初始化,dim是数组各维的长度dimnames是数组维的名字，默认为空，array(1:20, dim=c(4,5))。数组是多维的，dim属性设置维数

matrix(0, 3, 4)——0为赋初值，3行，4列，存储方式是先列后行！矩阵是二维的，用ncol和nrow设置矩阵的行数和列数。byrow设置存储方式（默认列优先），若为TRUE则以行优先

dim（<vector>）<- c(2,3)——设置矩阵为2行3列

dimnames（）=list(c（<row>），c（<col>）)——设置参数行和列的名称，以列表的形式进行输入

matrix[ ,4]——矩阵第4列

as.vector(matrix)——将矩阵转换成向量

a["name1","name2"]——矩阵以行和列的名称来代替行列的下标，name1是行名，name2是列名
 
rbind（）——矩阵合并，按行合并，自变量宽度应该相等

t()——矩阵转置

## 因子
因子和向量的区别：

向量里面存的元素类型可以是字符型，而因子里面存的是整型数值对应因子的类别（levels）

as.integer(<factors>)——因子可以转化为整型

gl（n，k，length）——因子,n为水平数，k为重复的次数，length为结果的长度

factor(x，levels，labels)——因子

as.factror()——将向量转化为无序因子，不能比较大小

as.order()——将向量转化为有序因子

is.factor()——判断是否为无序因子

is.order()——判断是否为有序因子

## 列表和数据框
list()——列表

data.frame()——数据框

names(<dataframe>)——显示数据框的列名称

dataframe[[2]] 和 dataframe[["TheSec.Name"]] 和  dataframe$TheSec.Name——获取数据框第二列的元素值

as.matrix(<dataframe>)[，1]——把数据框转化为矩阵后，再去提取列向量

!!! note "na和NULL的区别"

is.na()——判断na值存在，na是指该数值缺失但是存在。

is.null（）——判断数据是否为NULL。NULL是指不存在，可以通过 train$var<-NULL 的方法去掉属性变量var。

## 处理缺失数据na
1. 将缺失部分剔除
2. 用最高频率值来填补缺失值
3. 通过变量的相关关系来填补缺失值
4. 通过探索案例之间的相似性来填补缺失值


## 统计量
mean（x，trim=0,na,rm=FALSE）——均值，trim去掉x两端观测值的便利，默认为0，即包括全部数据，na.rm=TRUE允许数据中有缺失

median——中值

quantile(x，probs=seq(<start>,<end>,<diff>))——计算百分位数，是五数总和的扩展，probs设置分位数分位点，用seq(0,1,0.2)设置，表示以样本值*20%为间隔划分数据。

var（）——样本方差（n-1）

sd——样本标准差（n-1）

cov——协方差

cor——相关矩阵

## 数学函数
sum（x,y,z，na.rm=FALSE）——x+y+z，na.rm为TURE可以忽略掉na值数据

sum（x>4）——统计向量x中数值大于4的个数

rep（“LOVE！”，<times>）——重复times次，rep(1:3，c（1，2，3）)表示1个1，2个2，3个3组成的序列

sqrt（）——开平方函数

2^2 和 **——“^”幂运算

abs（）——绝对值函数

'%%'——表示求余 

'%/%'——求商（整数）

exp  ： 2.71828…

expm1  ： 当x的绝对值比1小很多的时候，它将能更加正确的计算exp(x)-1

log  ： 对数函数（自然对数）

log10  ： 对数（底为10）函数（常用对数）

log2  ： 对数（底为2）函数

sin  ： 正弦函数   
cos  ： 余弦函数   
tan  ：  正切函数   
asin  ：  反正弦函数   
acos  ：  反余弦函数   
atan  ：  反正切函数   
sinh  ：  超越正弦函数   
cosh  ：  超越余弦函数   
tanh  ：  超越正切函数   


## 简单分析
summary()——描述统计摘要，和 Hmisc()包的describe()类似，会显示NA值，四分位距是第1个（25%取值小于该值）和第3个四分位数（75%取值小于该值）的差值（50%取值的数值），可以衡量变量与其中心值的偏离程度，值越大则偏离越大。

## 单因子方差分析

```R
bac<-read.table("e:/ab.txt",header=T) # 读取数据
bac$type<-as.factor(bac$type) # 因子转换
ba.an<-aov(lm(day~type,data=bac)) # 单因素方差分析+回归拟合
summary(ba.an) # 概要分析
boxplot(day~type,data=bac,col="red") # 箱形图分析
```

## 柱状图

```R
barplot(grag,names.arg=months,xlab="month",ylab="faanshu",col=clors,main="total") # 作图
legend("topleft",cat,fill=clors,cex=1.5) # 图例
```