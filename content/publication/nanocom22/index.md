---
title: "Controlled Signaling and Transmitter Replenishment for MC with Functionalized Nanoparticles"
date: 2022-05-31
#publishDate: 2020-03-20T08:26:50.326574Z
authors: ["Maximilian Schäfer", "Lukas Brand", "Sebastian Lotter", "Atakan Büyüoglu", "Franz Enzenhofer", "Werner Haselmayr", "Kathrin Castiglione", "Dietmar Appelhans", "Robert Schober"]
publication_types: ["1"]
abstract: "In this paper, we propose novel Transmitter (Tx) models for Molecular Communication (MC) systems based on functionalized Nanoparticles (NPs). Current Tx models often rely on simplifying assumptions for the molecule release and replenishment mechanisms. In contrast, we propose a Tx model where the signaling molecule release is controlled by a switchable membrane driven by an external trigger. Moreover, we propose a reloading mechanism, where signaling molecules are harvested based on an enzymatic reaction. Hence, no repeated injection of signaling molecules is required. For the proposed system, we develop a general mathematical description in terms of a discrete-time transfer function model. Furthermore, we investigate two realizations of the proposed Tx model, i.e., an idealized Tx relying on simplifying assumptions, and a realistic Tx employing practical components for the reloading and release mechanisms. Finally, we numerically evaluate the proposed model and compare our results to stochastic Particle Based Simulation (PBS). "
featured: false
accompany: true
publication: "*submitted to 9th ACM International Conference on Nanoscale Computing and Communication*"
url_code: "https://github.com/maxschaefer-fau/TX-Signaling-Replenishment-MC"
url_demo: "/publication/TXsignal-replenish/"	

---

# Supplementary Material

### Contents:
1. Short summary of the proposed Transmitter (Tx) model including a description of the main features
2. Short summary of the practical realization of the proposed Tx model
3. Supplementary material for the Enzyme reaction and remarks on the implementation 

### 1. System Model 

As described in [1, Sec. 2], we propose a novel Transmitter (Tx) design for synthetic Molecular Communication (MC) systems employing functionalized Nanoparticles (NPs). The envisioned Tx comprises two main mechanisms namely 

- a __controlled release mechanism__, which enables the release of signaling molecules controlled by an external stimulus (see __Animation 1__, left hand side),
- a __reloading mechanism__ enabling the production of signaling molecules inside the Tx from molecules recruited from the surrounding environment (see Animation 1, right hand side).

{{< video src="videos/Animation5.mp4" controls="yes" >}}
__Animation 1__: <font size="4">Left hand side: Controlled release of signaling type B molecules (red) by controlled opening of the Tx membrane. Right hand side: Reloading of type A molecules (blue) from the surrounding environment and conversion into signaling type B molecules.</font>

Both, the __controlled release__ and the __reloading__ are facilitated by the design and functionalization of the NP. The __controlled release mechanism__ is realized by functionalization of the NP with a switchable membrane allowing for the control of its permeability by an external stimulus.
The __reloading mechanism__ is realized by enzymes encapsulated in the NP allowing for the conversion of molecules recruited from the surrounding environment, denoted as type A molecules, in signaling molecules, denoted as type B molecules. 
The switching of the NP membrane between the open and closed states is exploited for both the controlled release of type B molecules and the reloading of type A molecules, while the membrane is impermeable for enzymes in both states. 



### 2. Practical Realization of the proposed Tx Model 

In [1, Sec. 4] we describe a realization of the proposed Tx model based on practical components: 
- The __membrane switching__ for the controlled release is facilitated by polymersomes, the synthetic counterpart of liposomes, with a pH-driven permeability switch
- The __reloading mechanism__ (signaling molecule production) is realized by the encapsulation of the enzyme _Mandelate Racemase (MR)_ into the NP. MR performs a reversible one-substrate-reaction of _(R)-Mandelate_ (type A molecules) to _(S)-Mandelate_ (type B signaling molecule)
The switching process of the NP is shown below in __Animation 2__, cf. [1, Fig. 2]

{{< video src="videos/Animation4.mp4" controls="yes" >}}
__Animation 2__: <font size="4">Reloading and release process of the practical Tx model. Process flow:
	Only type (R)man molecules (blue) and enzymes (green) are present in the environment; 
	pH-decrease triggers the opening of the Tx membrane and (R)man molecules diffuse into the NP and are converted to (S)man signaling molecules (red); pH-increase triggers closing of the Tx membrane; pH-decrease triggers opening of the Tx membrane and the produced (S)man molecules are released while additional (R)man is harvested. 
    </font>

### 3. Supplementary Material - Enzyme Reaction

The enzyme _Mandelate Racemase (MR)_ performs a reversible one-substrate-reaction of _(R)-Mandelate_ (type A molecules) to _(S)-Mandelate_ (type B signaling molecule), and the reaction equations are as follows [2,3]
\begin{align}
&\ce{E + (R)man <=>[$k_1$][$k_{-1}$] E*(R)man <=>[$k_2$][$k_{-2}$] E*(S)man 
	<=>[$k_3$][$k_{-3}$]E + (S)man}, \\, \mathrm{(12)}
\end{align}
where E denotes the enzyme MR, and E$\cdot$(R)man and E$\cdot$(S)man denote intermediate complexes of MR and (R)man and (S)man, respectively. 
The corresponding reaction rates are denoted by $k_1, \\,k_2, \\,k_3$ and $k_{-1}, \\, k_{-2}, \\, k_{-3}$, respectively. 

#### Remarks on the Implementation 

As described in [1, Sec. 4], (12) cannot be solved analytically. Instead we developed a numerical model that is evaluated in each discrete time step. __The Python Code can be found on__ [GitHub](https://github.com/maxschaefer-fau/TX-Signaling-Replenishment-MC).
We obtained a numerical model as follows: 

##### Decomposition into three bidirectional reactions
First, we assume a pseudo steady state and derive a reaction rate equation for the three individual bidirectional reactions in [1, Eq. (12)] see, e.g., [4,5].

The individual bidirectional equations and the associated steady state reaction rate equations are as follows:

__Reaction 1__
The first bidirectional reaction in (12) follows as
\begin{align*}
&\ce{E + (R)man <=>[$k_1$][$k_{-1}$] E*(R)man} &&\mathrm{(12a)}.
\end{align*}
The associated reaction rate equation assuming a steady state follows as 
\begin{align*}
&\frac{\partial [E]}{\partial t} = 0, &k_{-1}[ER] - k_1[E][R] = 0, &&\mathrm{(12b)}
\end{align*}
where [E], [R], and [ER] denote the concentration of MR, (R)man, and E$\cdot$(R)man, respectively.

__Reaction 2__
The second bidirectional reaction in (12) follows as 
\begin{align*}
&\ce{E*(R)man <=>[$k_2$][$k_{-2}$] E*(S)man}. &&\mathrm{(12c)}
\end{align*}
The associated reaction rate equation assuming a steady state follows as 
\begin{align*}
&\frac{\partial [ER]}{\partial t} = 0, &k_{-2}[ES] - k_2[ER] = 0, &&\mathrm{(12d)}
\end{align*}
where [ER] and [ES] denote the concentration E$\cdot$(R)man and E$\cdot$(S)man, respectively.

__Reaction 3__
The third bidirectional reaction in (12) follows as 
\begin{align*}
&\ce{E*(S)man 
	<=>[$k_3$][$k_{-3}$]E + (S)man}. &&\mathrm{(12e)}
\end{align*}
The associated reaction rate equation assuming a steady state follows as 
\begin{align*}
&\frac{\partial [ES]}{\partial t} = 0, &k_{-3}[E][S] - k_3[ES] = 0, &&\mathrm{(12f)}
\end{align*}
where [E], [S], and [ES] denote the concentration of MR, (S)man and E$\cdot$(S)man, respectively.

For all three reaction rate equations (12b), (12d), (12f) a numerical model can be obtained straightforwardly, e.g., by numerical integration or by a solution in terms of an exponential approach. Further details on the exact numerical implementation of the individual bidirectional reactions can be found in the associated [Python code](https://github.com/maxschaefer-fau/TX-Signaling-Replenishment-MC).

##### Algorithm

Figure 1 shows the process of the developed algorithm to calculate the concentrations of all reaction partners in (12) by a sequential numerical evaluation of  (12b), (12d) and (12f) in the current time step $k$ from the concentrations in the previous time step $k-1$, where we denote the concentrations in time step $k$ according to (12b), (12d) and (12f) as follows:
\begin{align*}
[E]_k, \\, [R]_k, \\, [S]_k, \\, [ES]_k, \\, [ER]_k. 
\end{align*}

{{< figure src="img/reaction.png" caption="Algorithm to calculate concentrations in time step $k$ from previous time step $k-1$. Variables from the previous time step $k-1$, the current time step $k$ and auxiliary variables are highlighted blue, red, and green, respectively" numbered="true" >}}

<!---
__Conditions__
 The derived numerical model (see [GitHub](https://github.com/maxschaefer-fau/TX-Signaling-Replenishment-MC)) based on the decomposition of (12) is valid under the following conditions: 
- As the individual reaction parts are evaluated sequentially, the discrete time step ($T$ in [1]) has to be small enough (Also holds for other numerical integration methods)
- The backward and forward reaction rates are in a similar range which is fulfilled for the considered enzyme MR 

The validity of our developed numerical model is verified in [1] by the excellent agreement with the results obtained from Particle Based Simulation (PBS).
-->
<!---
##### Alternative Numerical Model 

Alternatively, a numerical model for the MR reaction can be obtained by transforming (12) fully into reaction rate equations without further assumptions. This leads to the set of Ordinary Differential Equations (ODEs):
\begin{align*}
\frac{\partial [E]}{\partial t} &= k_{-1}[ER] - k_1[E][R] + k_3 [ES] - k_{-3}[E][S],\\\
\frac{\partial [ER]}{\partial t} &= k_1 [E][R] - k_{-1} [ER] + k_{-2} [ES] - k_2 [ER],\\\
\frac{\partial [ES]}{\partial t} &= k_{-3} [E][S] - k_{3}[ES] + k_2 [ER] - k_{-2} [ES],\\\
\frac{\partial [R]}{\partial t} &= k_{-1}[ER] - k_1[E][R],\\\
\frac{\partial [S]}{\partial t} &= k_3[ES] - k_{-3} [E][S],
\end{align*}
where [E], [R], [S], [ER], and [ES], denote the concentration of MR, (R)man, (S)man, E$\cdot$(R)man and E$\cdot$(S)man, respectively.

This set of ODEs can be solved by different numerical methods, e.g., numerical integration or Euler Method, see [4] and references within for details.
-->
###  References 
[1] M. Schäfer, L. Brand, S. Lotter, A. Büyükoglu, F. Enzenhofer, W. Haselmayr, K. Castiglione, D. Appelhans and R. Schober, "_Controlled Signaling and Transmitter Replenishment for MC with Functionalized Nanoparticles_", submitted to 9th ACM Int. Conf. Nanosc. Comp. Commun. , 2022, [online]: TODO

[2] M. St. Maurice and S. L. Bearne. 2002. "_Kinetics and Thermodynamics ofMandelate Racemase Catalysis_". Biochem. 41, 12 (2002), 4048-4058. 

[3] Ariun Narmandakh and Stephen L. Bearne. 2010. "_Purification of Recombinant Mandelate Racemase: Improved Catalytic Activity_". Protein Expression and Purification, 69, 1 (2010), 39-46. https://doi.org/10.1016/j.pep.2009.06.022

[4] D. J. Higham. 2008. "_Modeling and Simulating Chemical Reactions_". SIAMRev. 50, 2 (2008), 347-368. https://doi.org/10.1137/060666457

[5] L. A. Segel and M. Slemrod. 1989. "_The Quasi-Steady-State Assumption: ACase Study in Perturbation_". SIAMRev. 31, 3 (1989), 446-477.