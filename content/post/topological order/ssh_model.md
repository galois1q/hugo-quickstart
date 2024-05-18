---
title: 'Su-Schrieffer-Heeger (SSH) model'

subtitle: 

summary: 'SSH model 简要回顾'

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

- name: 'Reference'

  url: https://arxiv.org/abs/1509.02295
---
### SSH Hamiltonian

SSH 模型：带有交错电子跃迁强度的双原子链，如下图所示：

<img src="/post/image/ssh_model/ssh_chain_bulkedge.svg">

只考虑电子跃迁而忽略电子电子相互作用，紧束缚模型给出的Hamiltonian如下：

$$
\hat{H}=\nu\sum_{m=1}^{N}(\left|m,B\right\rangle\left\langle m,A\right|+h.c.)+w\sum_{m=1}^{N-1}(\left|m+1,A\right\rangle\left\langle m,B\right|+h.c.).
$$

其中$\ket{m,\alpha},m=1,2\cdots ,N,\alpha=A,B$标记格点，而$\nu,\omega$标记跃迁强度，通过重定义态矢相位取正实数。

一维链模型总带边界，但我们更关心体（bulk）的性质，如在热力学极限系统的性质总是与边界条件选取无关。取周期性边界条件，bulk Hamiltonian为:

{{< math >}}  
$$
\hat{H}_{\mathbf{bulk}}=\sum_{m=1}^{N}(\nu\ket{m,B}\bra{m,A}+\omega\ket{(m\bmod N)+1,A}\bra{m,B})+h.c.
$$
{{< /math >}}  

薛定谔方程为：

$$
\hat{H}_\text{bulk}|\Psi_n(k)\rangle=E_n(k)\left|\Psi_n(k)\right\rangle
$$

为了求解bulk的本征波函数，我们利用Bloch定理，对位置$m$进行傅里叶变换：

{{< math >}}  
$$
\ket{k}=\frac{1}{\sqrt{N}}\sum\limits_{m=1}^{N}e^{imk}\ket{m},\quad\text{for}\,k\in\left\{\delta_k,2\delta_k,\ldots,N\delta_k\right\}\quad\text{with}\delta_k=\frac{2\pi}{N},
$$
{{< /math >}}  

其中 $k$仅在第一布里渊区取值，Bloch波函数为动量基底$\ket{k}$与原子基底 $\ket{\alpha}$的张量积：

$$
\ket{\Psi_{n}(k)}=\ket{k}\otimes\left|u_{n}(k)\right\rangle;\quad\left|u_{n}(k)\right\rangle=a_{n}(k)\left|A\right\rangle+b_{n}(k)\left|B\right\rangle.
$$

我们引入bulk动量空间哈密顿量 $\hat{H}(k)$使得 $\left|u_{n}(k)\right\rangle$构成其本征态：

{{< math >}}  
$$
\hat{H}(k)=\bra{k}\hat{H}_{\mathrm{bulk}}\ket{k}=\sum_{\alpha,\beta\in\left\{A,B\right\}}\bra{k,\alpha}H_{\mathrm{bulk}}\ket{k,\beta}\cdot\ket{\alpha}\bra{\beta};  
$$
{{< /math >}}  

{{< math >}}  
$$
\hat{H}(k)\ket{u_{n}(k)}  =E_{n}(k) \ket{u_{n}(k)} 
$$
{{< /math >}}  

坐标空间的晶格平移对称性在动量空间表现为：

$$
\hat{H}\left(k+2\pi\right)=\hat{H}\left(k\right);\quad\quad\quad\quad\left|u_n(k+2\pi)\right\rangle=\left|u_n(k)\right\rangle
$$

不难求得 $\hat{H}(k)$：

{{< math >}}  
$$
H(k)=\begin{pmatrix}0&v+we^{-ik}\\v+we^{ik}&0\end{pmatrix};\quad H(k)\begin{pmatrix}a(k)\\b(k)\end{pmatrix}=E(k)\begin{pmatrix}a(k)\\b(k)\end{pmatrix}.
$$
{{< /math >}}  

其能量本征值为：

$$
E(k)=\left|\nu+e^{-ik}w\right|=\sqrt{\nu^2+w^2+2\nu w\cos k}.
$$

色散关系图为：

![1706341978740](/post/image/ssh_model/1706341978740.png)

可以看出 $\nu<\omega$与 $\nu >\omega$的色散关系相似，但实际二者的拓扑不同。

能隙为 $2\Delta$,其中 $\Delta$为：

$$
\Delta=\min_kE\left(k\right)=\left|v-w\right|.
$$

### 拓扑相

$\hat{H}(k)$作为一个二能级系统总可以当作一个磁场的自旋 $\frac{1}{2}$粒子，利用Pauli矩阵改写Hamiltonian：

$$
H(k)=d_x(k)\hat{\boldsymbol{\sigma}}_x+d_y(k)\hat{\boldsymbol{\sigma}}_y+d_z(k)\hat{\boldsymbol{\sigma}}_z=d_0(k)\hat{\boldsymbol{\sigma}}_0+\mathbf{d}(k)\hat{\boldsymbol{\sigma}}
$$

其中 $\mathbf{d}(k)$相当于一个磁场，其形式为：

$$
d_x(k)=v+w\cos k;\quad d_y(k)=w\sin k;\quad d_z(k)=0.
$$

则本征函数利用二分量旋量表示为：

$$
|u_\pm(k)\rangle=\frac1{\sqrt{2}}\begin{pmatrix}1\\\pm e^{i\phi_k}\end{pmatrix}
$$

相应的Berry联络为：

{{< math >}}
$$
\mathcal{A}^{\pm}(k)=\langle u_{\pm}(k)|i\partial_{k}|u_{\pm}\rangle=\frac12\left(1\pm e^{-i\phi_{k}}\right)\begin{pmatrix}0\\\mp\frac{d\phi_{k}}{dk}e^{i\phi_{k}}\end{pmatrix}=\frac12\frac{d\phi_{k}}{dk}
$$
{{< /math >}}

利用Berry联络的积分Berry相位可以区分色散关系 $\nu<\omega$与 $\nu >\omega$：

- 平凡绝缘体 $\nu>\omega$：

{{< math >}}  
$$
\begin{aligned}\gamma=\oint\mathcal{A}^{\pm}(k)dk=\oint\frac{1}{2}\frac{d\phi(k)}{dk}dk=\frac{1}{2}\oint d\phi=\frac{\phi(\pi)-\phi(-\pi)}{2}=0\end{aligned}
$$
{{< /math >}}  

$k$转一圈磁场不绕原点转一圈。

- 拓扑绝缘体 $\nu<\omega$:

{{< math >}}  
$$
\begin{aligned}\gamma=\oint\mathcal{A}^{\pm}(k)dk=\oint\frac{1}{2}\frac{d\phi(k)}{dk}dk=\frac{1}{2}\oint d\phi=\frac{\phi(\pi)-\phi(-\pi)}{2}=\pi\end{aligned}
$$
{{< /math >}}

$k$转一圈磁场绕原点转一圈。

- 拓扑相：由于Berry相在绝热变化下不变，我们可以根据绝热变化下能否互相转化的态进行相分类，此时Berry相起到一个序参量的作用(*注意：Berry相并非局域的，这也是拓扑相区别于传统相的特征之一*)。

由此我们可以给出SSH model的相图：

![1706343569376](/post/image/ssh_model/1706343569376.png)

- 缠绕数：由于Berry phase反映的是SSH model 到磁场($S^1 \to S^1$) 的**连续映射**特征(取周期性边界条件一维链便构成了一维圆环 $S^1$)，即磁场绕原点转圈的次数，这个次数被称为winding number缠绕数 $W$.

{{< math >}}
$$
\left.W=\oint\frac{dk}{2\pi}\left[\mathbf{d}(k)\times\frac{d\mathbf{d}(k)}{dk}\right]_{\mathbb{Z}}=2\oint\frac{dk}{2\pi}\mathcal{A}(k)=\left\{\begin{array}{ll}0&\text{trivial}\\1&\text{non-trivial}\end{array}\right.\right.
$$
{{< /math >}}



### 手征对称性与边缘态

手征对称性 $\Gamma$定义为：

$$
\Gamma H\Gamma^{\dagger}=-H
$$

手征对称性要求 $d_z(k)\equiv 0$，在手征对称性下 $E_n$若为系统本征值，则 $-E_n$必然也是。

- 如果手征对称性存在，由于$\varepsilon_{\pm}(k)=\pm|\mathbf{d}(k)|=\pm\sqrt{d_{x}^{2}(k)+d_{y}^{2}(k)}>0$，绝缘体在 $\mathbf{d}$空间的圈不能跨过原点，即不绕原点的圈不能连续变形为绕原点的圈。
- 如果手征对称性破缺 $d_z(z)\neq 0$，则此时 可以通过第三维将不绕原点的圈连续变形为绕原点的圈，如下图所示。

![1706345728419](/post/image/ssh_model/1706345728419.png)

因此我们称**缠绕数受手征对称性保护。**

- 边缘态：
  尽管我们主要关心bulk的性质，但在拓扑非平凡时边缘态实际上零能构成费米面，具有一些奇特的性质。

研究边缘态最简单的情形是考虑二聚物极限，即取 $\nu\to 1,\omega\to 0$或 $\nu\to 0,\omega\to 1$,前者拓扑平凡后者拓扑非平凡，如下图所示：

<img src="/post/image/ssh_model/ssh_chain_flatbands.svg">

如果逐步取消二聚物极限：

![1706347357861](/post/image/ssh_model/1706347357861.png)

可以看出在 $\nu$较小的时候边缘态是二重简并的，在 $\nu$较大时边缘态不简并，在这个过程必然发生了一个解除简并的相变。而在取消二聚物极限的过程我们并不破坏系统的对称性，因此这种相变不能用朗道相变范式描述，这也是拓扑相变的非平凡之处。

- 体边对应：
  事实上**边缘态的数目 $N_A-N_B$也构成受手征保护的拓扑不变量**，这是由于在手征对称性下边缘态 $A,B$成对产生出现，差值总是固定的。边缘态数目反映系统的edge性质；而缠绕数只与系统的bulk有关，拓扑不变量的对应表明系统的体和边存在某种对应。
  <!-- 在量子霍尔效应中这种对应更为深刻，边缘态由手征共形场论描述，而体态由高一维的拓扑场论给出其有效场论；这种对应实际反映的是体的反常需要和边界的手征反常相消。 -->
