---
title: '拓扑序与量子序(一)'
subtitle: 对称性破缺
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
## 对称性破缺

---

### 自发对称性破缺与相变


- 量子多体系统：Hilbert space  $V_{tot}=\otimes_{i=1}^{N}V_i$+ Hamiltonian  $H=\sum_x{H_x}$. 态矢量是单体态矢量的张量积, 而Hamiltonian是单体Hamiltonian的直和.

Example:

$$
H=J\sum_{i=x,y,z}\sigma_{1}^{i}\sigma_{2}^{i}
$$

此处实际是缩写, $\sigma_{i}^z=I\otimes \cdots\otimes I\otimes\sigma^z\otimes I\otimes\cdots\otimes I$

对于环 L上的横向Ising model：

$$
H=-J\sum_{i=1}^L \sigma_{i}^x \sigma_{i+1}^x -h \sum_{i=1}^L \sigma_{i}^z
$$

从能谱看出h较小基态出现二重简并,简并的出现解除暗示了相变.

![横场哈密顿量的能谱](/post/image/topo1/fig1.png)

- 相变的刻画：对于参数化的哈密顿量 $H(g)$, 若 $g$改变在 $g_c$处 基态能量 $\epsilon_g=E_g/v$ 或算符期望出现了奇异性, 则 $g_c$处出现了相变.

  - 有限系统无奇异性, 无限大系统才可能出现奇点；
  - 可以利用自发对称性破缺机制产生相变；
- 利用自发对称性破缺,也可以半经典地理解奇异性的出现, 在对基态能量求变分若 $g_c$处 $\epsilon_c(g)''$出现奇异, 则出现相变.

![相变奇异性出现示意图](/post/image/topo1/fig2.png)

- 横场Ising模型的对称性破缺：
  取试探波函数 $\ket{\Psi_\phi}=\otimes_i\ket{\psi_i},\ket{\psi_i}=\cos\frac{\phi}{2}\ket{\uparrow}+\sin\frac{\phi}{2}\ket{\downarrow}$, 估计的基态能量为：
  {{< math >}}

$$
\begin{array}{l}\epsilon_h(\phi)=\langle\Psi_\phi|H|\Psi_\phi\rangle\\
=-\sum\langle\psi_i|\sigma_i^x|\psi_i\rangle\langle\psi_{i+1}|\sigma_{i+1}^x|\psi_{i+1}\rangle
-h\sum\langle\psi_i|\sigma_i^z|\psi_i\rangle\\=(2J\cos\frac\phi2\sin\frac\phi2)^2-h(\cos^2\frac\phi2-\sin^2\frac\phi2)=\sin^2\phi-h\cos\phi\end{array}
$$

 {{< /math >}}
存在 {{< math >}}$\mathbb{Z}_{2}${{< /math >}}对称性, {{< math >}}$\epsilon_h(\phi)=\epsilon_h(-\phi)${{< /math >}}, {{< math >}}$U=\prod_{j}\sigma_j^z${{< /math >}} (on-site symmetry), $\color{red}{|\psi\rangle\not\propto U|\psi\rangle}$时对称性破缺.
    - $\ket{\Psi_{\phi=0}}$ 作为基态——对称相；
    - $\ket{\Psi_{\phi\neq 0}}$ 作为基态——对称破缺相.

由于 {{< math >}}$\mathbb{Z}_{2}${{< /math >}}  对称性下 $\sigma_i^x\to-\sigma_i^x$, 可以选取 $\langle\sigma_i^x\rangle$作为序参量, 序参量的改变对应相变.

> remark:考虑量子效应, 实际上有限大系统基态存在隧穿并不会真正地对称性破缺,基态并不完全简并, 能隙 $\Delta \sim e^{-L/\xi}$.

### 量子激发与准粒子

- 激发态与准粒子：对于多体系统 $H_0=\sum_x H_x$带有基态 $\ket{\Psi_{ground}}$, 准粒子激发对应 $\xi$附近出现非零局域能量密度；更严格地考虑在 $\xi_i$ 处能用局域势阱 $\delta H_{\xi_i}$可俘获的激发即准粒子激发, 此时  $\ket{\Psi_{\xi_i}}$对应**有能隙**的 $H_0+\sum_i \delta H_{\xi_i}$的基态.
- 局域激发与拓扑激发：
  - $\xi_1$处的局域激发：若激发可以从基态由局域算符产生：  $\ket{\Psi_{\xi_1,\xi_2,\cdots}}=  O_{\xi_1}\ket{\Psi_{\xi_2,\cdots}}$;
  - $\xi_1$处的拓扑激发：非局域激发即拓扑激发.

Example: 1D横场Ising模型,基态设为：

$$
\left|{\Psi_0}\right\rangle  =|\uparrow\uparrow\uparrow\uparrow\uparrow\uparrow\uparrow\uparrow\uparrow\uparrow\uparrow\uparrow>
$$

则一个三粒子激发即：

$$
|\Psi_{\xi_1\xi_2\xi_3}\rangle  =|\uparrow\uparrow\downarrow\uparrow\uparrow\uparrow\downarrow\downarrow\downarrow\uparrow\uparrow\uparrow> \\
$$

$\xi_1$处局域激发（自旋翻转产生激发）, $\xi_{2,3}$处拓扑激发(畴壁产生激发), 可由弦算符描述 ${W_{\xi_2\xi_3}=\prod_{i=\xi_2}^{\xi_3}\sigma_i^x}$.

Example: 1D spin dimmer state, 系统带有 $SO(3)$对称性, 基态由自旋单态构成spin-dimmer,此时平移对称性破缺.
{{< math >}}

$$
\begin{aligned}
&(\uparrow\downarrow)(\uparrow\downarrow)(\uparrow\downarrow)(\uparrow\downarrow)(\uparrow\downarrow)(\uparrow\downarrow)(\uparrow\downarrow) \\
&\cdots (\uparrow\downarrow)(\uparrow\downarrow)(\uparrow\downarrow)(\uparrow\downarrow)(\uparrow\downarrow)(\uparrow\downarrow)(\uparrow\downarrow)\cdots 
\end{aligned}
$$

{{< /math >}}
局部激发=自旋-1激发：

$$
(\uparrow\downarrow)(\uparrow\downarrow)(\uparrow\downarrow)\uparrow\uparrow(\uparrow\downarrow)(\uparrow\downarrow)(\uparrow\downarrow)(\uparrow\downarrow)
$$

拓扑激发=自旋-1/2激发(spinon)：

$$
(\uparrow\downarrow)(\uparrow\downarrow)\uparrow(\uparrow\downarrow)(\uparrow\downarrow)(\uparrow\downarrow)\uparrow(\uparrow\downarrow)(\uparrow\downarrow)
$$

- 2D Spin liquid without symmetry breaking：

{{< math >}}

$$
\begin{aligned}{\mathbb{Z}_2}\text{-charge }(\text{spin-}1/2)&=\text{Spinon. }\\
{\mathbb{Z}_2}\text{-vortex }(\text{spin-}0)&=\text{Vison}.\\
\mathrm{Bound~state}&=\text{fermion (spin-}1/2).\end{aligned}
$$

{{< /math >}}

![spinon 链示意图](/post/image/topo1/fig3.png)
在自旋液体中, Spinon显得没有电荷差异但有自旋差异.

- Spinon实验测量：domain wall有$2J$能隙,但自旋翻转(等价于成对domain wall)对应局部算符测量的 $4J$能隙；中子散射作为局部算符翻转自旋, 只能测量 $4J$能隙(测量局部激发)；而比热 $C\sim e^{-\Delta \beta}$ 可以测量拓扑激发.
