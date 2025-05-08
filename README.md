# Research-Log
**这是用来整理平时科研过程中自己的想法，和别人合作时各方的讨论结果以及问题整理的一个模版。平时在开组会活着与同学讨论过程中总会有一些想法，顺便可以整理记录，时间久了应该也能从中找出一些不错的点子。**

我这里的模版是基于[project-logbook](https://github.com/apalha/project-logbook)进行了一些改造。它是一个英文版本，就是用来写科研日志的，我在这里进行了中文化，并对其中的一些环境进行了修改，对高亮色块的颜色配置进行了修改。

# Meeting
首先是***Meeting*环境
```latex
\begin{Meeting}{会议日期}{main}%最后一个参数是作者id，用来标记这次会议是谁的想法
这里是一次会议讨论内容的记录，主导者第一个作者，用mian来作为他的id。在这次讨论中有一个重要任务先要完成
\hightodo{日期}{main}{这里是目前最优先要做的事情，这些事情都会被加入到最后的todo list 中 }
\end{Meeting}
```
这个环境块主要是用来整理一下会议或者讨论的记录，其中可以标记出会议的主导者。同时也能利用
```latex
\hightodo{日期}{main}{这里是目前最优先要做的事情，这些事情都会被加入到最后的todo list 中 }
```
高亮出讨论中最重要，优先级最高的需要解决的问题。

# Note(Think)
这个环境块和**Meeting**没有太大本质上的区别，就是进行了颜色上的区分，可以给这个**Note**环境一个标题，用来提醒自己这个Note要说明什么问题。同样还有一个**Think**环境块，也只是修改了一下颜色而已。

这里还有一个**lotodo**，用来区别前面的**hightodo**，二者的颜色是不同的，代表了需要完成的事情的优先级是不同的，相当于是要高亮一下提醒自己需要做的事情，
```latex
\lowtodo{日期}{abc}{这里是目前次优先要做的事情 ，这些事情都会被加入到最后的todo list 中}
```
![png](https://github.com/yxli8023/Research-Log/blob/main/figures/demo-1.png)

最后在文档最后面会生成一个**Todo List**，这里面就包含了前面使用**hightodo**和**lowtodo**来提醒自己需要做的事情，方便自己在整理科研日志的时候来提醒自己，同时也可以将一些想法高亮出来，说不定什么时候就可以有一些突破性的进展。
![png](https://github.com/yxli8023/Research-Log/blob/main/figures/demo-2.png)

# 代码插入
通过`python`环境块可以直接插入程序语言，而且其中每一行都会有编号。这里测试了一下，往里面写`Julia`语言也是可以的，其它语言没有进行测试

![png](https://github.com/yxli8023/Research-Log/blob/main/figures/python.png)

```latex
\begin{python}
	Hoff1 = zeros(ComplexF64,2 * N,2 * N)  # off-diagonal element
	Hoff2 = zeros(ComplexF64,2 * N,2 * N)
	for k2 in -tr:tr,j2 in -tr:tr,k1 in -tr:tr,j1 in -tr:tr
	if k1 == k2 &&  j1 == j2
	off1 = zeros(ComplexF64,N,N)
	off1[(k1 + tr) * s + j1 + tr + 1,(k2 + tr) * s + j2 + tr + 1] = 1
	Hoff1 +=  kron(off1,Tb)
	off2 = zeros(ComplexF64,N,N)
	off2[(k2 + tr) * s + j2 + tr + 1,(k1 + tr) * s + j1 + tr + 1] = 1
	Hoff2 += kron(off2,Tb')
	elseif k1 == k2 && j1  + 1 == j2
	off1 = zeros(ComplexF64,N,N)
	off1[(k1 + tr) * s + j1 + tr + 1,(k2 + tr) * s + j2 + tr + 1] = 1
	Hoff1 += kron(off1,Ttr)
	off2 = zeros(ComplexF64,N,N)
	off2[(k2 + tr) * s + j2 + tr + 1,(k1 + tr) * s + j1 + tr + 1] = 1
	Hoff2 += kron(off2,Ttr')
	elseif k1 - 1 == k2 && j1 == j2
	off1 = zeros(ComplexF64,N,N)
	off1[(k1 + tr) * s + j1 + tr + 1,(k2 + tr) * s + j2 + tr + 1] = 1
	Hoff1 += kron(off1,Ttl)
	off2 = zeros(ComplexF64,N,N)
	off2[(k2 + tr) * s + j2 + tr + 1,(k1 + tr) * s + j1 + tr + 1] = 1
	Hoff2 += kron(off2,Ttl')
	end
	end
	Hoff = kron([0 1;0 0],Hoff1) + kron([0 0;1 0],Hoff2)
\end{python}
```


# 未待续完
暂时这个模版满足了我的基本需求，还没有其他的想法可以加入到这个模版中，后面如果有新东西，我会继续更新。如果你在科研进程中有什么好的整理日志的方式，可以联系我，如果在我能力范围内，我会努力将这个功能加入到当前的模版中。

# 联系我

**e-mail:yxliphy@gmail.com**

