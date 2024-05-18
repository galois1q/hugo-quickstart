---
title: '拓扑序与量子序(三)'
subtitle: 量子Hall效应的有效场论
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
## 导出Chern-Simons项的“穷人”方法

### 朗道相变理论复习

朗道二级相变理论告诉我们当发生自发对称性破缺时，假设对称群从$G\to G/ H$，则局域序参量 $\phi$将会给出非零的期望值。为了研究对称性破缺过程，我们可以根据对称性写下一个低能有效理论，如最简单的带有$\mathbb{Z}_2$对称性的拉式量 $\mathcal{L}$(或自由能 $F$)的一般形式为：

$$
\mathcal{L}\sim a\phi^2+b\phi^4+\cdots
$$

假设随着 $a,b$关于某些参数 $T$的改变，系统的极小值从一个变成两个，那么系统选择其中一个作为真空重新构造低能有效理论时，系统的对称性便被隐藏起来了，序参量的期望值从零变为非零，此时我们称系统发生了相变。**当然我们之所以称系统发生相变，更重要的是系统对外加微扰会产生不同的响应,当然这宏观表现序参量的变化，进一步也表现为序参量关于外加微扰导数的变化。**

如考虑外加磁场 $h$下我们可以构造一个响应自由能为 $f(h)$,磁化强度 $M$ 是响应自由能 $f$ 对外加磁场的 $h$线性响应(线性响应理论)：

$$
M=-\frac{\partial f}{\partial h},\quad \text{(负号只是符合热力学习惯)}
$$

我们并不知道$f(h)$的基本形式(这是非常尴尬的一件事情，当然如果我们知道 $f(h)$，后面一段也没有必要了),但这个 $f(h)$可以看作只用系统性质磁化强度$M$描述的自由能(设为 $G(M)$)在外界磁场 $h$响应下的有效自由能。

按照最小线性耦合原理 $G$应当表示为：

$$
G(M)=f(h)+M\cdot h
$$

容易看出 $\frac{\partial G}{\partial M}=h$。尽管读者可能意识到以上不过是对Legendre变换的复述，但这种响应自由能的思想是有效理论的精髓，实际我们后面的内容很大程度上只是把上述内容推广到路径积分形式罢了。

那么 $G$的基本形式是什么？答案是靠猜，我们可以根据对称性写下 $G$可能的基本形式：

$$
G=A(T)+B(T)M^2+C(T)M^4,\quad(C>0)
$$

如果 $T<T_c,B(T)>0$自由能 $G$只有一个极小值，而  $T>T_c,B<0$自由能 $G$有两个极小值。设 $B(T)=b\cdot (T-T_c),C(T)=c$，则 $G$极小值处的磁化强度为：

$$
M=\begin{cases}
  0&T>T_C;\\\pm\bigl[\frac{b}{2c}(T_C-T)\bigr]^{1/2}&T<T_C.
  \end{cases}
$$

外加磁场 $h$与磁化率的隐式关系为：

$$
h=2b(T-T_c)M+4cM^3
$$

而磁化率 $\chi=(\frac{\partial M}{\partial h})_T$,即：

$$
\chi=\frac{1}{2b(T-T_c)+12cM^2}=\begin{cases}
  \frac{1}{2b(T-T_c)},&T\ge T_c \\
  -\frac{1}{2b(T_c-T)},&T\le T_c
\end{cases}
$$

最后一个括号在临界温度 $T_c$附近线性近似，可以看出磁化率也发生了突变，不同的相的磁化率也在外加磁场下产生了不同的响应。

---

### 分数Hall效应的有效理论

当试图把朗道相变理论这一套推广到拓扑相变时，最大的问题在于我们找不到有效的局域序参量。尽管如此，我们依然可以尝试构建有效的响应作用量。


#### 外加磁场下的响应作用量
我们考虑一个 $d=2+1$维的外加 $z$磁场 $B$的 $x-y$平面霍尔元件，我们对系统添加一个外加微扰项 $\delta \vec{A}$改变外磁场，需要强调的是$\delta \vec{A}$是**非动力学**的，也就是它只是一个经典的外加微扰而非一个规范势。

由欧姆定律 {{< math >}}$\vec{J}_H=\sigma^{xy}\vec{E}\times \hat{z}${{< /math >}},和电荷守恒微分形式 {{< math >}}$\frac{\partial \rho}{\partial t}+\nabla \cdot \vec{J}_{H}${{< /math >}},容易求得:

{{< math >}}
$$
\begin{cases}
  \vec{J}_H &=\sigma^{xy}\vec{E}\times \hat{z} \\
  \rho_H &= \sigma^{xy}\delta \vec{B}
\end{cases}
$$
{{< /math >}}

用四维矢量流 $J^{\mu}_{H}=(\rho_H,\vec{J_H})$可以表示为:

{{< math >}}
$$
J^{\mu}_{H}=\sigma^{xy}\partial_{\nu}\delta A_{\lambda}\epsilon^{\mu\nu\lambda}
$$
{{< /math >}}

按照之外的想法，我们希望一个找到一个响应作用量 $S_{eff}[\delta A]$，通过线性响应给出正确的电流：

{{< math >}}
$$
J^{\mu}_{H}\equiv \frac{\partial S_{eff}[\delta A_{\mu}]}{\partial [\delta A_{\mu}]}
$$
{{< /math >}}

此处忽略期望值符号，即 {{< math >}}$J^{\mu}_{H}\equiv \left\langle J^{\mu}_{H}\right\rangle ${{< /math >}},而 {{< math >}}$S_{eff}[\delta A_{\mu}]${{< /math >}}
是将所有动力学变量积掉的低能有效作用量。但不同于之前的朗道相变理论，我们此时是已知响应 {{< math >}}$J^{\mu}_{H}$ {{< /math >}} 的形式去猜测 {{< math >}}$S_{eff}[\delta A_{\mu}]${{< /math >}}, 最简单的耦合方式是 {{< math >}}$J^{\mu}_{H}\delta A_{\mu}${{< /math >}},由此猜测“最经济的”有效作用量为：

$$
S_{eff}[\delta A_{\mu}]=\frac{\sigma_{xy}}{2}\int \mathrm{d}^3x\delta A_\mu \partial_{\nu}\delta A_{\lambda}\epsilon^{\mu\nu\lambda}
$$

> Remark: 
>- 1/2因子用于移除重复求和；
>- $S_{eff}[\delta A_{\mu}]$我们称其为经典Chern Simons项，注意此时我们始终把 $\delta A_\mu$当作经典背景场而非动力学场，也并未谈及规范场的量子化，即 $\sigma_{xy}$是任意的.
>- 经典CS项不是规范不变的，这一点后面详述。
>- 如果我们想要利用经典CS项得到整数Hall效应，则在欧氏度规(Wick 转动)下需要将时空紧致化为 $S^1\times S^2$。配分函数的规范不变性要求Hall电导系数的量子化。

#### Bulk的动力学作用量

我们进一步需要分析是怎样的体作用量在外加响应下给出上述有效作用量。和前面对称性破缺讨论类似，我们选取体电流作为动力学变量；同时我们希望作用量尽可能简单实用，最简单的形式之一便是Gauss型：

$$
S[j]=\frac{1}{2}\int \mathrm{d}^3x j_{\mu}(x)M^{\mu \nu}j_{\nu}(x)
$$

有效作用量通过路径积分下积掉动力学场 $j$给出：

{{< math >}}
$$
\begin{aligned}
Z &=\int \mathcal{D}[j]\mathcal{D}[\delta A]\exp (i S[j]+i \int \mathrm{d}^3x j_\mu \delta A^{\mu})\\
&=\int \mathcal{D}[\delta A] \exp (i S_{eff}[\delta A^{\mu}])
\end{aligned}
$$
{{< /math >}}

由Gauss积分公式可得 ：

{{< math >}}
$$
(M^{-1})_{\nu \lambda}=\sigma^{xy}\epsilon_{\mu\nu\lambda}\partial^{\nu}
$$
{{< /math >}}

在欧式度规下， $j$守恒给出 $\partial_{\mu}j^{\mu}=0$。我们可以自然地猜测 $j$电流由背后的某个动力学规范场 $a^{\mu}$生成，利用 $a^{\mu}$自然地可以将 $j_{\mu}$表示为：

$$
j^{\mu}=\frac{1}{2}\epsilon^{\mu\nu\lambda}\partial_{\nu} a_{\lambda}=\frac{1}{2\pi \sigma_{xy}}(M^{-1})^{\mu\lambda}a_{\lambda}
$$

接下来我们需要计算 $M$的表达式，这样我们就完全把 $S[j]$确定下来了。然而 $M^{-1}$实际存在零模式：

{{< math >}}
$$
(M^{-1})_{\nu \lambda}(\partial^{\lambda}\theta)=\sigma^{xy}\epsilon_{\mu\nu\lambda}\partial^{\nu}\partial^{\lambda}\theta=0
$$
{{< /math >}}

这说明 $M^{-1}$并不可逆，实际需要做规范固定去除零模式。当然由于 $j \propto M^{-1}a$，实际计算 $S[j]=S_{CS}[a]$时 $M$会自动消去，给出CS项：

{{< math >}}
$$
S[j]=S_{CS}[a]=\frac{1}{8\pi^{2}\sigma_{xy}}\int \mathrm{d}^{3}x a_\mu \partial_\nu a_\lambda \epsilon^{\mu\nu\lambda}
$$
{{< /math >}}

这样我们就得到了外场 $\delta A^{\mu}$微扰下完整的体拉式量密度：

$$
\boxed{\mathcal{L}=\frac{1}{8\pi^{2}\sigma_{xy}} a_\mu \partial_\nu a_\lambda \epsilon^{\mu\nu\lambda}+\frac{1}{2\pi}\delta A_\mu \partial_\nu a_\lambda \epsilon^{\mu\nu\lambda}}
$$

### Hall电导的量子化

为了简化记号，定义 $\sigma_{xy}=\frac{1}{m}\frac{e^{2}}{h}$;使用外微分符号 $\wedge$,则CS项记作：

$$
S_{CS}=\frac{m}{4\pi}\int a \wedge \mathrm{d} a
$$

一个重要的事实在于CS项并不是规范不变的