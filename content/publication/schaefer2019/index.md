---
title: "Feedback Structures for a Transfer Function Model of a Circular Vibrating Membrane  "
date: 2019-10-01
publishDate: 2019-07-20T08:26:50.326574Z
authors: ["Maximilian Schäfer", "Sebastian J Schlecht", "Rudolf Rabenstein"]
publication_types: ["1"]
abstract: "The attachment of feedback loops to physical or musical systems enables a large variety of possibilities for the modification of the system behavior. Feedback loops may enrich the echo density of feedback delay networks (FDN), or enable the realization of complex boundary conditions in physical simulation models for sound synthesis. Inspired by control theory, a general feedback loop is attached to a model of a vibrating membrane. The membrane model is based on the modal expansion of an initial-boundary value problem formulated in a state-space description. The possibilities of the attached feedback loop are shown by three examples, namely by the introduction of additional mode wise damping; modulation and damping inspired by FDN feedback loops; time-varying modification of the system behavior."
featured: false
accompany: true
publication: "*Proc. IEEE Workshop Applicat. Signal Process. Audio Acoust. (WASPAA)*"
url_demo: "/publication/schaefer2019/"
---








### Block Diagram

<img src="BlockDiagram.png" width="600"/>

<strong>**Figure 1:**</strong> State-space description of the 2D circular membrane in the frequency domain (switch open $\widehat{=}$ open loop system) and the attached feedback loop (switch closed $\widehat{=}$ closed loop system).



### Audio Examples

We present various examples of feedback configurations for the proposed system of the circular membrane for sound synthesis.


## Damping Only
In the following, we apply time-invariant damping only in the feedback via the diagonal matrix $\mathcal{D} = \textrm{diag}( \dots, d_{\mu}, \dots ) $ and $\mathcal{U} = 0$. 

| Damping Type                | Damping Coefficients                 |
|-----------------------------|--------------------------------------|
| No Damping                  | $d_{\mu} = 0$                      |
| Equal Damping               | $d_{\mu}= -2$                      |
| Frequency-dependent Damping | $d\_{\mu} = -0.001 \cdot k_{n,m}^2/R_0^2$ |
| Tension-like Modulation     | $d\_{\mu} = 0.05j \cdot k_{n,m}^2/R_0^2$ |


<div class="player">
  <p>
      Sound example with various damping feedback loop.
  </p>
  <ts-track title="Original" data-img="">
      <ts-source src="https://dl.dropboxusercontent.com/s/poxmmtf6sl5kbuw/plateExamples_config_01.m4a?dl=0" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Equal Damping" data-img="">
      <ts-source src="https://dl.dropboxusercontent.com/s/dzet0nthvnt8tpa/plateExamples_config_02.m4a?dl=0" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Frequency-dependent Damping" data-img="">
      <ts-source src="https://dl.dropboxusercontent.com/s/nmlitqx3evahzd5/plateExamples_config_03.m4a?dl=0" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Tension-like Modulation" data-img="">
      <ts-source src="https://dl.dropboxusercontent.com/s/3q6t17k0nvbxnww/plateExamples_config_04.m4a?dl=0" type="audio/mpeg"></ts-source>
  </ts-track>
</div>



## Time Variation

In the following, we apply time-variant coupling only in the feedback via the matrix $\gamma\_\textrm{U}[k] \cdot \mathcal{U}$ with $\gamma\_\textrm{U}[k] = \alpha \sin( \beta \, k 2\pi T)$, where $\alpha$ denotes the time-variation amplitude and $\beta$ denotes the time-variation frequency in Hertz ($\mathcal{D} = 0$).

| Feedback Matrix Type | Time variation Amplitude $\alpha$| Time variation Frequency $\beta$   |
|----------------------|----------------------------------|------------------------------------|
| Identity             | 0.00                             | 0                                  |
| Hadamard             | 0.01                             | 5                                  |
| Hadamard             | 0.05                             | 5                                  |
| Hadamard             | 0.02                             | 15                                 |
| Random Orthogonal    | 0.02                             | 15                                 |

<div class="player">
  <p>
      Sound example with various strength of time-variation.
  </p>
  <ts-track title="Original" data-img="">
      <ts-source src="https://dl.dropboxusercontent.com/s/poxmmtf6sl5kbuw/plateExamples_config_01.m4a?dl=0" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Subtle Variation with Hadamard Matrix" data-img="">
      <ts-source src="https://dl.dropboxusercontent.com/s/ojo0th68s2n908z/plateExamples_config_05.m4a?dl=0" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Slow, and large variation with Hadamard Matrix" data-img="">
      <ts-source src="https://dl.dropboxusercontent.com/s/1ejdlzjakitbdmj/plateExamples_config_06.m4a?dl=0" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Fast, but small variation with Hadamard Matrix" data-img="">
      <ts-source src="https://dl.dropboxusercontent.com/s/abrb0xfcm0dteqf/plateExamples_config_07.m4a?dl=0" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Fast, but small variation with Random Orthogonal Matrix" data-img="">
      <ts-source src="https://dl.dropboxusercontent.com/s/edpwkhijj7l1c89/plateExamples_config_08.m4a?dl=0" type="audio/mpeg"></ts-source>
  </ts-track>
</div>

## Experimental Configurations

In the following, we apply time-variant coupling only ($\mathcal{D} = 0$) in the feedback via the matrix with similar parameters as above, but more experimental settings.

| Feedback Matrix Type | Time variation Amplitude $\alpha$| Time variation Frequency $\beta$   |
|----------------------|----------------------------------|------------------------------------|
| Identity             | 0.00                             | 0                                  |
| Hadamard             | 0.05                             | 1.5                                |
| Random Orthogonal    | 0.11                             | 0.1                                |
| Random Householder   | 0.11                             | 1.5                                |
| Householder with Ones| 0.11                             | 1.5                                |



<div class="player">
  <p>
      Sound example with more experimental settings.
  </p>
  <ts-track title="Original" data-img="">
      <ts-source src="https://dl.dropboxusercontent.com/s/poxmmtf6sl5kbuw/plateExamples_config_01.m4a?dl=0" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Hadamard Matrix with tension-like damping" data-img="">
      <ts-source src="https://dl.dropboxusercontent.com/s/qqr7warneftc3yy/plateExamples_config_09.m4a?dl=0" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Random Orthogonal Matrix" data-img="">
      <ts-source src="https://dl.dropboxusercontent.com/s/urnqhv0o0hsszst/plateExamples_config_10.m4a?dl=0" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Random Householder Matrix" data-img="">
      <ts-source src="https://dl.dropboxusercontent.com/s/2t5f10xoad6mnys/plateExamples_config_11.m4a?dl=0" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Householder One Matrix" data-img="">
      <ts-source src="https://dl.dropboxusercontent.com/s/p2gayy5rmacu6ap/plateExamples_config_12.m4a?dl=0" type="audio/mpeg"></ts-source>
  </ts-track>
</div>


### Credits

[Trackswitch.js](https://audiolabs.github.io/trackswitch.js/) was developed by Nils Werner, Stefan Balke, Fabian-Rober Stöter, Meinard Müller and Bernd Edler. 


<script src="https://cdn.rawgit.com/download/polymer-cdn/1.5.0/lib/webcomponentsjs/webcomponents-lite.min.js"></script>
<script src="https://code.jquery.com/jquery-3.2.1.min.js" integrity="sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=" crossorigin="anonymous"></script>
<script src="/js/trackswitch.js"></script>
<script type="text/javascript">
	var $j = jQuery.noConflict();
    $j(document).ready(function() {
        // $j(".customplayer").trackswitch({ onlyradiosolo: true, repeat: true });
        $j(".player").trackSwitch({ onlyradiosolo: true, repeat: true, spacebar: true  });
    });
</script>	