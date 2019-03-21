# 第一课 Marlab入门基础

Matlab中文官网：https://ww2.mathworks.cn/

Release Notes：https://ww2.mathworks.cn/help/matlab/release-notes.html

## 变量命名规则
- 变量名区分大小写
- 变量名长度不超过63位
- 变量名以字母开头，可以由字母、数字和下划线组成，但不能使用标点
- 变量名应简洁明了，通过变量名可以直观看出变量所表示的物理意义

## 数据类型：
- 数字
- 字符与字符串
- 矩阵
- 元胞数组
- 结构体

```matlab
clear all    % 清空全部变量
clc    % 清空工作区

doc num2str  % 查看帮助文档
```
- Ctrl+R 注释
- Ctrl+T 取消注释

## 矩阵操作
- 矩阵的定义与构造
- 矩阵的四则运算
- 矩阵的下标

## 逻辑与流程控制
- if... else... end
- for... end
- while... end
- switch... case... otherwise... end

## 脚本与函数文件
- 脚本文件
- 函数文件

## 基本绘图操作
- 二维平面绘图
- 三位立体绘图
- 图形的保存与导出

## 文件导入
- mat格式
- txt格式
- xls格式
- csv格式

# 第二课 Matlab进阶与提高

## 编程习惯与风格
- 变量的命名规则
- Cell Mode  %% 分段
- 程序发布（Publish） html格式
File / Publish ....m

## Errors
- Index must be a positive integer or logical.
- Undefined function or variable "B".
- Inner matrix dimensions must agree.
- Function definitions are not permitted at the prompt or in scripts.
- Index out of bounds because numel(A) = 5.
- In an assignment A(I) = B, the number or elements in B and I must be the same.
- Expression or statement is incorrect--possibly unbalanced (,{,or[.
- Too many input arguments.

## 程序调试-断点调试
- 设置/清除断点
断点调试时，要注释掉'clear all'
Step(F10)
- 进入/退出调试模式
- 循环体的调试
把出错前的全都运行一遍，从出错的那一步设置断点，进行调试

## 如何充分利用网络资源
- www.mathworks.com/matlabcentral/fileexchange/
- www.ilovematlab.cn
- Some tips:
再现问题：完整的错误信息、源程序文件、数据等
帖子标题：简要说明问题的本质，勿出现“跪求”、“xx大神/大侠”...

## 如何查看、编辑Matlab自带的工具箱函数？
- edit
- varargin/varagout/nargin/nargout
**varagin**: Variable length input argument list.
**varargout**: Variable length output argument list.
**nargin**: Numver of input arguments specified for a function.
**nargout**: Number of output arguments specified for a function.

## 内存优化配置
- memory/feature memstats 查看
- 禁用Java虚拟机
- 增加虚拟内存数量
- 打开系统3GB开关（32位系统）（推荐）
=》我的电脑/属性/高级/启动和故障恢复/设置/编辑

## 向量化编程
- 及时清除不用的变量
- 使用变量前，预先分配内存空间
- 选择恰当的数据类型
- 循环与向量化
按列优先循环；
循环次数多的变量安排在内层。
- 给一些函数“瘦身”

## 图像对象和句柄
- 图形对象：用于界面制作和数据可视的基本绘图元素。
- 图形对象是图形系统中最基本、最底层的单元。
- 图形对象的属性由属性名和属性值两部分组成。
- 句柄是图形对象的标识代码，句柄含有图形对象的各种必要的属性信息。
- 根屏幕的句柄为0，图形窗口的句柄为整数，其他对象的句柄为浮点型
数。

Root
- Figure
-- UI Objects
-- Axes
--- Core Objects
--- Plot Objects
--- Group Objects
-- Hidden Annotation Axes
---Annotation Objects




# 第三课 BP神经网络



# 第四课 RBF、GRNN和PNN神经网络



# 第五课 竞争神经网络与SOM神经网络



# 第六课 支持向量机（Support Vector Machine，SVM）



# 第七课 极限学习机（Extreme Learning Machine，ELM）



# 第八课 决策树与随机森林






# 第九课 遗传算法（Genetic Algorithm，GA）

- 遗传算法(Genetic Algorithm, GA)是一种进化算法，其基本原理是仿效生物界中的“物竞天择，适者生存”的演化法则，它最初由美国Michigan大学的J.Holland教授于1967年提出。

- 遗传算法是从代表问题可能潜在的解集的一个**种群（population）**开始的，而一个种群则由经过基因（gene）编码的一定数目的**个体（individual）**组成。因此，第一步需要实现从表现型到基因型的映射即编码工作。初代种群产生之后，按照适者生存和优胜劣汰的原理，逐代（generation）演化产生越来越好的近似解。在每一代，根据问题域中个体的**适应度（fitness）**大小选择个体，并借助于自然遗传学的遗传算子（genetic operators）进行组合交叉和变异，产生出代表新的解集的种群。这个过程将导致种群像自然进化一样，后生代种群比前代更加适应环境，末代种群中的最优个体经过解码（encoding），可以作为问题近似最优解。

## 遗传算法有3个基本操作：选择(Selection)、交叉(Crossover)和变异(Mutation)

1. **选择**。选择的目的是为了从当前群体中选出优良的个体，使它们有机会作为父代为下一代繁衍子孙。根据各个个体的适应度值，按照一定的规则或方法从上一代群体中选择出一些优良的个体遗传到下一代种群中。选择的依据是适应性强的个体为下一代贡献一个或多个后代的概率大。

2. **交叉**。通过交叉操作可以得到新一代个体，新个体组合了父辈个体的特性。将群体中的各个个体随机搭配成对，对每一个个体，以交叉概率交换他们之间的部分染色体。

3. **变异**。对种群中的每一个个体，以变异概率改变某一个或多个基因座上的基因值为其他的等位基因。同生物界中一样，变异发生的概率很低，变异为新个体的产生提供了机会。

## 遗传算法的基本步骤

1. **编码**：GA在及性能搜索之前先将解空间的解数据表示成遗传空间的基因型串结构数据，这些串结构数据的不同组合便构成了不同的点。

2. **初始种群的生成**：随机产生N个初始串结构数据，每个串结构数据称为一个个体，N个个体构成了一个种群。GA以这N个串结构数据作为初始点开始进化。

3. **适应度评估**：适应度表明个体或解的优劣性。不同的问题，适应性函数的定义方式也不同。

4. **选择**：选择的目的是为了从当前群体中选出优良的个体，使它们有机会作为附带为下一代繁殖子孙。遗传算法通过选择过程体现这一思想，进行选择的原则是适应性强的个体为下一代贡献一个或多个后代的概率大。选择体现了达尔文的适者生存原则。

5. **交叉**：交叉操作时遗传算法中最主要的遗传操作。通过交叉操作可以得到新一代个体，新个体组合了其父辈个体的特性。交叉体现了信息交换的思想。

6. **变异**：变异首先在群体中随机选择一个个体，对于选中的个体以一定的概率随机地改变串结构数据中某个串的值。同生物界一样，GA变异发生的概率很低，通常取值很小。

## 遗传算法工具箱

- Matalb内嵌遗传算法工具箱：gadst

- Sheffield大学遗传算法工具箱：gatbx

- **北卡罗来纳大学遗传算法工具箱：gaot**

## 重点函数解读

- optimtool (matlab自带)

- **initializega** (gaot)

- **ga** (gaot)

- normGeomSelect (gaot)

- arithXover (gaot)

- nonUnifMutation (gaot)

## Demo

- 一元函数优化

- BP神经网络初始权值和阈值优化

### 先导入工具箱： file-set path-add

# 第十课 粒子群优化（Particle Swarm Optimization，PSO）算法

- 粒子群优化（PSO, particles swarm optimization）算法时计算智能领域，除了蚁群算法、鱼群算法之外的一种群体智能的优化算法。该算法最早由Kennedy和Eberhart在1995年提出，源自对鸟类捕食问题的研究。

- PSO算法首先在可行解空间中初始化一群粒子，每个粒子都代表极值优化问题的一个潜在最优解，**用位置、速度和适应度值三项指标表示该粒子特征**
。

- 粒子在解空间中运动，通过跟踪**个体极值Pbet**和**群体极值Gbest**更新个体位置，个体极值Pbest是指个体所经历为之中计算得到的适应度值最优位置，群体极值Gbest是指种群中的所有粒子搜索到的适应度最优位置。

- 粒子每更新一次位置，就计算一次适应度值，并且通过比较新粒子的适应度值和个体极值、群体极值的适应度值更新个体极值Pbest和群体极值Gbest的位置。

- 在每一次迭代过程中，粒子通过个体极值和群体极值更新自身的速度和位置，更新公式如下：![图10.1 粒子速度、距离更新公式]()

## 粒子群优化算法与遗传算法对比

### 相同点：

- 种群随机初始化

- 适应度函数值与目标最优解之间的映射

### 不同点：

- PSO算法没有选择、交叉、变异等操作算子

- PSO有记忆的功能

- 信息共享机制不同。遗传算法是互相共享信息，整个种群的移动是比较均匀地向最优区域移动。而在PSO中，只有gBest或IBest给出信息给其他粒子，属于单向的信息流动，**整个搜索更新过程是跟随当前最优解的过程**。因此，**在一般情况下，PSO的收敛速度更快**。

## Demo

- 一元函数优化

- 二元函数优化

### 工具箱

- 2014b以后版本，自带PSO工具箱

- PSOt工具箱，psopt工具箱，等


# 第十一课 蚁群算法（Ant Colony Algorithm，ACA）

- 蚁群算法(Ant Colony Algorithm, ACA)由Marco Dorigo于1992年在他的博士论文中首次提出，该算法模拟了自然界中蚂蚁的觅食行为。

- 蚂蚁在寻找食物源时，会在其经过的路径上释放一种信息素，并能够感知其他蚂蚁释放的信息素。
**信息素浓度的大小表征路径的远近，信息素浓度越高，表示对应的路径距离越短**。

- 通常，蚂蚁会以较大的概率优先选择信息素浓度较高的路径，并释放一定量的信息素，以增强该条路径上的信息素浓度。这样，会形成一个**正反馈**。最终，蚂蚁能够找到一条从巢穴到食物源的最佳路径，即距离最短。

- 值得一提的是，生物学家同时发现，**路径上的信息素浓度会随着时间的推进而逐渐衰减**。

- 将蚁群算法应用于解决优化问题，其基本思路为：**用蚂蚁的行走路径表示待优化问题的可行解，整个蚂蚁群体的所有路径构成待优化问题的解空间**。路径较短的蚂蚁释放的信息素量较多，随着实践的推进，较短的路径上积累的信息素浓度逐渐增高，选择该路径的蚂蚁个数也愈来愈多。最终，整个蚂蚁会在正反馈的作用下集中到最佳的路径上，此时对应的便是待优化问题的最优解。

## 蚁群算法的特点

- 采用正反馈机制，使得搜索过程不断收敛，最终逼近于最优解。

- 每个个体可以通过释放信息素来改变周围的环境，且每个个体能够感知周围环境的实时变化，个体间通过环境进行间接地通讯。

- 搜索过程采用分布式计算方式，多个个体同时进行并行计算，大大提高了算法的计算能力和运行效率。

- 启发式的概率搜索方式，不容易陷入局部最优，易于寻找到全局最优解。

## 旅行商问题(TSP)

### 重点函数解读

- `doc ismemeber`

- `doc cumsum`

- `doc num2str`

- `doc text`

# 第十二课 模拟退火算法（Simulated Annealing，SA）

## 模拟退火算法(Simulated Annealing, SA)的思想最早是由Metropolis等提出的。其出发点是基于物理中固体物质的退火过程与一般的组合优化问题之间的相似性。模拟退火是一种通用的优化算法，其物理退火过程由以下三个部分组成。

- **加温过程**。其目的是增强粒子的热运动，使其偏离平衡位置。当温度足够高时，固体将熔为液体，从而消除系统原先存在的非均匀状态。

- **等温过程**。对于与周围环境交换热量而温度不变的封闭系统，系统状态的自发变化总是朝自由能减少的方向进行的。当自由能达到最小时，系统达到平衡状态。

- **冷却过程**。使粒子热运动减弱，系统能量下降，得到晶体结构。

- 加温过程对算法**设定初温**，等温过程对应算法的**Metropolis抽样过程**，冷却过程对应**控制参数的下降**。这里能量的变化就是目标函数，我们要得到的最优解就是能量最低态。其中Metropolis准则是SA算法收敛于全局最优解的关键所在，Metropolis准则以一定的概率接受恶化解，这样就使得算法跳离局部最优的陷阱。

![pic12.1 SA process]()

## 模拟退火算法的特点

- 与遗传算法、粒子群优化算法和蚁群算法不同，模拟退火算法不属于群优化算法，不需要初始化种群操作。

- 收敛速度较慢。

- 温度管理、退火速度等对寻优结果均有影响。

## Demo

- 一元函数优化

`optimtool`

Solver: Simulannealbnd - Simulated annealing algorithm

Objective function: @fitness

Max iteration: Specify: 100

Annealing function: Boltzmann annealing

Plot function: all selected

- 多元函数优化

- TSP优化

## Exploration vs. Exploitation


# 第十三课 降维与特征选择


