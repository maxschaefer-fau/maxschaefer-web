---
title: "Controlled Signaling and Transmitter Replenishment for MC with Functionalized Nanoparticles"
date: 2022-05-31
#publishDate: 2020-03-20T08:26:50.326574Z
authors: ["Maximilian Schäfer", "Lukas Brand", "Sebastian Lotter", "Atakan Büyüoglu", "Franz Enzenhofer", "Werner Haselmayr", "Kathrin Castiglione", "Dietmar Appelhans", "Robert Schober"]
publication_types: ["2"]
abstract: "In this paper, we propose novel Transmitter (Tx) models for Molecular Communication (MC) systems based on functionalized Nanoparticles (NPs). 
Current Tx models often rely on simplifying assumptions for the molecule release and replenishment mechanisms. 
In contrast, we propose a Tx model where the signaling molecule release is controlled by a switchable membrane driven by an external trigger.
Moreover, we propose a reloading mechanism, where signaling molecules are harvested based on an enzymatic reaction.
Hence, no repeated injection of signaling molecules is required.
For the proposed system, we develop a general mathematical description in terms of a discrete-time transfer function model. 
Furthermore, we investigate two realizations of the proposed Tx model, i.e., an idealized Tx relying on simplifying assumptions, and a realistic Tx employing practical components for the reloading and release mechanisms.
Finally, we numerically evaluate the proposed model and compare our results to stochastic Particle Based Simulation (PBS). "
featured: false
accompany: true
publication: "*submitted to 9th ACM International Conference on Nanoscale Computing and Communication*"
url_code: "https://github.com/maxschaefer-fau/TX-Signaling-Replenishment-MC"
url_demo: "/publication/TXsignal-replenish/"	

---

### Contents:
1. Preliminaries
2. Videos of the propagation of the particles in the cylinder for a [*uniform release*](#2-uniform-release-of-particles) supplementary to Fig. 4 (see [[1, Sec. V-D]](#7-references))
3. Videos of the propagation of the particles in the cylinder for a [*point release*](#3-point-release-of-particles) supplementary to Fig. 5 (see [[1, Sec. V-E]](#7-references))
4. Videos of the propagation of the particles in the cylinder for [*analysis of accuracy*](#analysis-of-accuracy) (see [[1, Sec. VI-B]](#7-references))
5. Remarks regarding the [*implementation*](#5-implementation) (see [[1, Sec. VI-A]](#7-references))
6. [*Performance analysis*](#6-analysis-of-runtime-and-complexity)
7. [*References*](#7-references) 


### System Model 

#### Overall System Model 

#### Reloading Mechanism 


### Chemical Reaction 

The enzyme _Mandelate Racemase (MR)_ performs a reversible one-substrate-reaction of _(R)-Mandelate_ (type A molecules) to _(S)-Mandelate_ (type B signaling molecule), and the reaction equations are as follows [2,3]
$$ 
\ce{E + (R)man <=>[$k_1$][$k_{-1}$] E*(R)man <=>[$k_2$][$k_{-2}$] E*(S)man 
	<=>[$k_3$][$k_{-3}$]E + (S)man},
$$
where E denotes the enzyme MR, and E$\cdot$(R)man and E$\cdot$(S)man denote intermediate complexes of MR and (R)man and (S)man, respectively. 
The corresponding reaction rates are denoted by $k_1, \\,k_2, \\,k_3$ and $k_{-1}, \\, k_{-2}, \\, k_{-3}$, respectively. 

#### Reaction Rate Equations 

\begin{align*}
\frac{\partial [E]}{\partial t} &= k_{-1}[ER] - k_1[E][R] + k_3 [ES] - k_{-3}[E][S],\\\
\frac{\partial [ER]}{\partial t} &= k_1 [E][R] - k_{-1} [ER] + k_{-2} [ES] - k_2 [ER],\\\
\frac{\partial [ES]}{\partial t} &= k_{-3} [E][S] - k_{3}[ES] + k_2 [ER] - k_{-2} [ES],\\\
\frac{\partial [R]}{\partial t} &= k_{-1}[ER] - k_1[E][R],\\\
\frac{\partial [S]}{\partial t} &= k_3[ES] - k_{-3} [E][S],
\end{align*}
where [E], [R], [S], [ER], and [ES], denote the concentration of MR, (R)man, (S)man, E$\cdot$(R)man amd E$\cdot$(S)man, respectively.

#### Solution 1

#### Solution 2

#### Remarks on the Implementation 




### 1. Preliminaries

We note that the variables in the presented formulas are defined in [[1]](#7-references).

#### 1.1 Summary of the proposed model

The considered advection-diffusion problem with laminar flow is mathematically described by the PDE [[1, Eq. (4)]](#7-references) 
\begin{align*}
\frac{\partial}{\partial t}p(\mathbf{x},t) = D \mbox{div}\left(\mbox{grad}\left( p(\mathbf{x},t)\right)\right) - \mbox{div} \left(p(\mathbf{x},t) v(r)\mathbf{e}_z\right),
\end{align*}
with the radius dependent flow velocity [[1, Eq. (5)]](#7-references) 
\begin{align*}
v(r) = v_0\left(1 - \frac{r^2}{R_0^2}\right).
\end{align*}





<!--alpha 1e-1-->
<script>
function setvideo_p01(src) {
    document.getElementById('div_video_p01').innerHTML = '<video autoplay controls id="video_ctrl_p01"><source src="'+src+'" type="video/mp4"></video>';
    document.getElementById('video_ctrl_p01').play();
}
</script>

|$\alpha$         		|Eigenvalues            | Release type 		| 
| ------------------		| --------------------- | ---------------------	| 
|$\alpha = 0.1$| $Q = 12.6\cdot 10^{4}$, $\mathbf{q} = [20, 30, 200]$ | point |


<button onClick="setvideo_p01('./point_alpha_1e-1_re075.mp4');">$r_e = 0.75$</button>
<button onClick="setvideo_p01('./point_alpha_1e-1_re05.mp4');">$r_e = 0.5$</button>
<button onClick="setvideo_p01('./point_alpha_1e-1_re025.mp4');">$r_e = 0.25$</button>
<div id="div_video_p01"> </div>

- For $Q = 100$ and $Q = 20$ the reflections become stronger and are not attenuating, instead they are propagating in the cylinder and interfere the concentration at the receiver, see black and orange curves in [[1, Fig. 8a]](#7-references).


##### 4.3.2 Point release of particles

The following videos correspond to the scenario in Fig. 8b, i.e., a point release of particles for different values of $Q$.

|$\alpha$         		|Eigenvalues            | Release type 		| 
| ------------------		| --------------------- | ---------------------	| 
|$\alpha = 1 \cdot 10^{-2}$ | varied | point |

**The videos for a specific number of eigenvalues $Q$, defined by vector $\mathbf{q}$ are selected by clicking on the corresponding button**
### 7. References 
[1] M. Schäfer, L. Brand, S. Lotter, A. Büyükoglu, F. Enzenhofer, W. Haselmayr, K. Castiglione, D. Appelhans and R. Schober, "_Controlled Signaling and Transmitter Replenishment for MC with Functionalized Nanoparticles_", submitted to 9th ACM Int. Conf. Nanosc. Comp. Commun. , 2022, [online]: TODO

[2] M. St. Maurice and S. L. Bearne. 2002. "_Kinetics and Thermodynamics ofMandelate Racemase Catalysis_". Biochem. 41, 12 (2002), 4048-4058. 

[3] Ariun Narmandakh and Stephen L. Bearne. 2010. "_Purification of Recombinant Mandelate Racemase: Improved Catalytic Activity_". Protein Expression and Purification, 69, 1 (2010), 39-46. https://doi.org/10.1016/j.pep.2009.06.022