---
title: '拓扑序与量子序(二)'
subtitle: 多体系统的拓扑序
summary: '寇享课程学习笔记'
authors:
  - admin
tags: [凝聚态物理]
categories: []
projects: []
date: 'today'
lastMod: 'today'
image:
  caption: ''
  focal_point: ''
links: 
- name: '图片来源与课程链接'
  url: https://www.koushare.com/live/topology
---

## 多体系统的拓扑序

朗道二级相变理论作为凝聚态物理的重要基石，解释了很多现象，其基本思想为自发对称相变由序参量和系统哈密顿量$H$对称性群 $G_H$破缺到基态对称性群 $G_{\Psi}\subset G_{H}$刻画。

但在分数量子霍尔效应（FQH）中朗道范式并不能很好地描述系统，向系统添加杂质有可能做到改变系统对称性但不改变分数霍尔平台的出现，即系统基态存在某种微扰不变的性质。如何对不同FQH系统进行分类引出了拓扑序的概念提出。

---

### 拓扑序的引入

- 量子物质（quantum matter）指  $T=0$系统的相，根据能谱可以做如下简单分类：

  - no low energy excitations (Insulator) $\rightarrow$ trivial
  - some low energy excitations (Superfluid) $\rightarrow$ interesting
  - a lot of low energy excitations (Metal) $\rightarrow$ messy

  拓扑序属于第一类，基态和激发态存在能隙而无低能激发，这样的体系关联函数长程下均趋于零，几乎没有可测量的物理量，看起来很平凡，一个可测的物理量是基态简并度。
- 拓扑序的刻画：
  由于不能利用关联函数直接刻画拓扑序，而直接考虑基态波函数其过于复杂，需要寻找一个合适的方法刻画基态简并度。关键思想在于把有能隙系统放到不同拓扑空间测量基态简并度，不同的拓扑空间基态简并度不同，**即基态简并度给出了拓扑序的宏观刻画。**
  进一步需要给出拓扑序的微观描述，由于系统基态简并在任意局域微扰下不变，简并为**拓扑简并**，这表明基态简并度与传统的对称群无关。
- 拓扑序的起源：
  多体系统的重要特征之一是其高度纠缠的，*仅仅知道其局域性质无法刻画整个系统(不同的纠缠态可以有相同的约化密度矩阵，而带有局域相互作用的Hamiltonian仅仅可以测量约化密度矩阵)*。利用**拓扑纠缠熵和长程纠缠**将可以给出拓扑序。

  ---

  Example:
- 简单直积态与纠缠态：

$$
\begin{aligned}
&\mid\uparrow\rangle\otimes\mid\downarrow\rangle+\mid\downarrow\rangle\otimes\mid\uparrow\rangle\rightarrow\text{entangled (quantum)} \\
&|\uparrow\rangle\otimes|\uparrow\rangle+|\downarrow\rangle\otimes|\downarrow\rangle+|\uparrow\rangle\otimes|\downarrow\rangle+\|\downarrow\rangle\otimes|\uparrow\rangle  \\
&{=(|\uparrow|+|\downarrow\rangle)\otimes(|\uparrow|+|\downarrow\rangle)=|x\rangle\otimes|x\rangle}\to\text{unentangled}
\end{aligned}
$$

- 反铁磁态无纠缠 $|\downarrow\rangle\otimes|\uparrow\rangle\otimes|\downarrow\rangle\otimes|\uparrow\rangle\otimes|\downarrow\rangle...$
  ![1705807582615](/post/image/topo2/1705807582615.png)
- spin dimmer短程纠缠 ${(|\downarrow\uparrow\rangle-|\uparrow\downarrow\rangle)\otimes(|\downarrow\uparrow\rangle-|\uparrow\downarrow\rangle)\otimes...}$
![1705807780055](/post/image/topo2/1705807780055.png)
- 晶体结构无纠缠
  $|{\Phi_{\mathrm{crystal}}}\rangle=\left|\boxed{{\vdots\vdots\vdots}}\right>=|{0}\rangle_{{x_1}}\otimes|{1}\rangle_{{x_2}}\otimes|{0}\rangle_{{x_3}}\cdots $
- 超流态无纠缠

  $|{\Phi_{\mathrm{SF}}}\rangle=\sum_{\mathrm{all~conf.}}\left|\boxed{{\vdots\vdots\vdots}}\right>=(|0\rangle_{x_1}+|1\rangle_{x_1}+..)\otimes(|0\rangle_{x_2}+|1\rangle_{x_2}+\cdots )\cdots $

---

### 长程纠缠

- 长程纠缠与长程纠缠物质：以上例子表明纠缠要么是局域的要么系统不纠缠，定义无法通过局域幺正变换得到的纠缠态为长程纠缠态(LRE)，反之短程纠缠态(SRE)可以通过局域幺正变换互相联系，SRE属于同一相，而LRE可以属于不同相。**拓扑序的局域描述可以由LRE给出。**

![1705808572063](/post/image/topo2/1705808572063.png)

> Remark(经典拓扑与量子拓扑)
>
> - 经典拓扑：能带的扭曲变形；
> - 量子拓扑：多体波函数纠缠的局域扰动不变性；

- 长程纠缠态的构造：
  - 无权重态叠加得到直积态：${\sum_{\text{all spin config.}}|\uparrow\downarrow..\rangle=|\to\to..\rangle}$
  - 带权展相位因子叠加可能得到长程纠缠态：${\sum_{\text{all spin config.}}\prod_{i<j}(z_i^\uparrow-z_j^\uparrow)^m|\uparrow\downarrow..\rangle}$
    (手征自旋液体或FQH态)
  - 部分自旋构型的求和可能得到长程纠缠态：如将向上自旋称作背景，考虑向下自旋连起来的弦叠加可以构造长程纠缠的弦液体：
    ![1705810494311](/post/image/topo2/1705810494311.png)
    进一步可以引入相位权展构造更复杂的态：
    ![1705810472028](/post/image/topo2/1705810472028.png)

尽管构LRE态看起来简单，但是物理上还关心相应的局域哈密顿量，弦液体的局域哈密顿量构造实际上由张量范畴给出。

- 弦液体的基态局部规则：

  1. 基态由闭弦刻画；
  2. 闭弦可以形变，也可断裂再重新闭合:
     ![1705810896194](/post/image/topo2/1705810896194.png)
     由于可以从单个闭弦不断的断裂重新连接得到其他闭弦，因此闭弦的全局波函数为：
     ![1705811187362](/post/image/topo2/1705811187362.png)

  - Hamiltonian构造要求
    1. 弦的开闭需要消耗能量；
    2. 弦可以自由地跳跃和重新连接。
       由此满足局部规则的态能量最低必然是基态。
- (另一种)弦液体的基态局部规则：

  1. 基态由闭弦刻画；
  2. 闭弦可以形变，也可断裂再重新闭合:
     ![1705811460216](/post/image/topo2/1705811460216.png)
     由于在2维每次重新形成一个闭弦必然增加一个因子 $(-)$,故全局波函数为：
     ![1705811574511](/post/image/topo2/1705811574511.png)
- 拓扑激发：开弦的端点表现为点粒子，由于激发总是成对出现，这种激发是拓扑的。弦的端点是没有内部自由度，比如固定四个端点在  $S^2$上，内部自局部自由度表现为弦的简并。由于局部规则2两种固定方式是等价的，故实际无简并，即端点激发无内部自由度。
- （第一种自旋液体）拓扑激发类型：由于弦通过自旋反转构造，弦是boson型的；对弦作 $2\pi$转动，有：
  ![1705918830688](/post/image/topo2/1705918830688.png)
  第一个弦实际上要转 $2\pi$角度才能恢复原位，有两种基本激发：
  ![1705918899837](/post/image/topo2/1705918899837.png)
  通过交换弦端点，拓扑激发实际上可以涌现出自旋统计定理：
  ![1705919040209](/post/image/topo2/1705919040209.png)
  我们称该自旋液体带有 $\mathbb{Z}_2$拓扑序。
- （第二种自旋液体）拓扑激发类型：对弦作 $2\pi$转动，有：
  ![1705919176666](/post/image/topo2/1705919176666.png)
  两种拓扑激发为：
  ![1705919235602](/post/image/topo2/1705919235602.png)
  我们称该自旋液体带有 double semion拓扑序。

### 弦网液体

- 弦网液体：允许三个弦相连，但不允许弦有端点。
![1705919477420](/post/image/topo2/1705919477420.png)
- 拓扑激发：了解拓扑激发首先需要知道弦端点能否有内部自由度，仍旧考虑固定四个弦端点在 $S^2$上对sector计数，此处需要利用融合规则（fusion rule）才能给出正确的计数：
  ![1705919665735](/post/image/topo2/1705919665735.png)
  可以看出仅有两种局部无法区分的态，我们称其构成一个 **qubit**.

  对于 $S^2$上固定的 $n$个端点，应该存在 $D_n$个局部不可区分态，计算 $D_n$即利用融合规则计算 $n-2$个端点的独立融合可能性(剩下两个端点必然连接起来)：
  ![1705920041941](/post/image/topo2/1705920041941.png)
  上述构成Fibonacci数列，即：

  $$
  F_n=F_{n-1}+F_{n-2},\quad D_n=F_{n-2}
  $$

  我们将弦的端点激发称作Fibonacci anyon，考虑 $n$固定下的大 $n$极限，$D_n\sim \mathrm{lim}_{n\to \infty}d^n$,我们称 $d$为 **量子维数**(经典维数应该给出 $2^n=D_n$)。

  $$
  {d=\lim_{n\to\infty}\frac{D_n}{D_{n-1}}=\lim_{n\to\infty}\frac{F_n}{F_{n-1}}}=\frac{\sqrt{5}+1}{2}
  $$
- 分数统计：非整数的量子维数暗示非整数的量子自由度，量子统计实际上反映的是交换全同粒子的相位差异，**准确来说量子统计实际由编织而非交换定义**(Yong-Shi Wu):

  1. 平凡辫子群表示：Boson
  2. 一维辫子群表示：Fermion or Anyon
  3. 高维辫子群表示：Non-Abelian Anyon
