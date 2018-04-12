## 画图
从邻接矩阵到有向图，需要使用以下几个包：NetworkX、Matplotlib (or pylab)、numpy(非必需)。

### NetworkX
 NetworkX 是一个用于生成、操作和研究复杂网络的结构，动态和功能的 python 包。[NetworkX 官网](https://networkx.github.io/)。在使用 python 画图的过程中，添加图的边，顶点，权重，属性，透明度等，都需要借助这个包。
 
### Matplotlib
简单来说，Matplotlib 是 Python 的一个绘图库，基于 numpy 包。它包含了大量的工具，你可以使用这些工具创建各种图形，包括简单的散点图，正弦曲线，甚至是三维图形。Python 科学计算社区经常使用它完成数据可视化的工作。[Matplotlib 官网](https://matplotlib.org/)。

最简单是示例：

``` python
import networkx as nx
import pylab 
import numpy as np
import matplotlib.pyplot as plt

G = nx.DiGraph()									# 新建有向图
G.add_nodes_from('012')								# 添加顶点
G.add_edges_from([('0','1'),('0','2'),('1','2')])	# 添加边
nx.draw(G)											# 生成图
# ![](/assets/Figure_1.png)nx.draw(G,with_labels=True)							# 带标签
# pylab.show()										# 画图
plt.show()
```

![](/assets/Figure_1.png)


参考：
 1. [python networkx 包绘制复杂网络关系图](https://www.jianshu.com/p/e543dc63454f)
 2. [十分钟入门 Matplotlib](http://codingpy.com/article/a-quick-intro-to-matplotlib/)