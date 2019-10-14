Maze
--------
由于老师已经把maze的大部分函数实现了，仅留下了maze2的solvemaze功能等未实现，
因此我所做的主要工作是将maze2的功能补完，并且修改了一下原本的代码以解决部分问题。目前已经实现的功能有:  
+ *findFNeighbours2*与*findFNeighbours2New*函数  
*findFNeighbours2*函数将当前节点的周围至多8个符合类型条件的节点按照从左到右，从上到下的顺序依次放入栈中，并返回该栈。  
*findFNeighbours2New*函数按照目标节点相对当前节点的位置，采用不同的入栈顺序。一般情况下最可能找到最短路径的方向先入栈，然后返回该栈。
+ *solveMaze2*与*solveMaze2New*函数  
*solveMaze2*函数采用dfs的方法搜索起点到终点的路径，对当前节点调用*findFNeighbours2*函数并将返回子赋给一个栈*neighbours*，
再将当前节点入栈*stack*，从*neighbors*取出第一个节点作为新的当前节点，然后开始递归，直到当前节点的坐标与目标节点的坐标相同位置。  
*solveMaze2New*函数采用类似A\*算法的方法，对当前节点调用*findFNeighbours2New*，在一般情况下可以达到优化算法的目的。  
由于两种方法是同时分别在*canvas1*与*canvas2*上进行以达到对比的目的，所以增加了参数*index*取值分别为**0**或**1**代表*canvas1*和*canvas2*，调
用函数时则为：  
```javascript
solveMaze2(0);
solveMaze2New(1);
```
+ 其他函数功能的补全与修改   
由于增加了与maze2有关的几个函数，其他的函数如*onCreate*、*getCursorPos*中需要加上对于maze2的相应功能。  
另外，由于实际运行时发现的部分问题，我对其他函数也做了一些修改：  
 1. 如在绘制迷宫和路径的时候禁用**Create**按钮和鼠标；
 2. 绘制结束后需点击依次**clear**按钮才能进行下一次选点；
 3. 以及在许多地方增加了*start*坐标的复原；  
---------
其他还有一些功能和问题，由于本人能力不足，也没有在网上找到比较好的解答，因此未能更好地完善本次作业。或许在更加熟悉js和html的语法和操作之后
这些问题能够得到解决。

