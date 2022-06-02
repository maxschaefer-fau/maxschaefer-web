---
title: "A String in a Room: Mixed-Dimensional Transfer Function Models for Sound Synthesis"
date: 2020-03-20
publishDate: 2020-03-20T08:26:50.326574Z
authors: ["Maximilian Schäfer",  "Rudolf Rabenstein", "Sebastian J Schlecht"]
publication_types: ["1"]
abstract: "Physical accuracy of virtual acoustics receives increasing attention due to renewed interest in virtual and augmented reality applications.
So far, the modeling of vibrating objects as point sources is a common simpliﬁcation which neglects effects caused by the spatial extent.
In this contribution, we propose a technique for physical modeling of distributed sources and their radiation into the environment. 
In particular, we consider the modeling of a guitar string oscillating in a two-dimensional room. 
The room and the string rely on well established physical descriptions that are modeled in terms of transfer functions. 
The connection of string and room is given by a connection matrix that deﬁnes the coupling between the characteristic string and room modes.
The proposed structure is analyzed by numerical evaluations and sound examples on the supplementary website."
featured: false
accompany: true
publication: "*International Conference on Digital Audio Effects (DAFx 2020)*"
url_code: "https://github.com/SebastianJiroSchlecht/MixedDimensionFTM/"	

aliases:
    - /publication/String-In-Room/

---


### A String is not a Point Source

In this first animation, we present the spatio-temporal behavior of a string:
<video poster="" title="" controls="controls" style="" width="640" height="">
	<source src="https://dl.dropboxusercontent.com/s/752i2e9ygm4zzop/string_animation.mp4?dl=0" />Your browser does not support this video format.
</video>

In the next step, this string is picked up at a certain position (dashed line) and emitted into a room via an omnidirectional source:
<video poster="" title="" controls="controls" style="" width="640" height="">
	<source src="https://dl.dropboxusercontent.com/s/z658nx5mijt31cd/animatePointStringInRoom.mp4?dl=0" />Your browser does not support this video format.
</video>

Now, instead of the point source modeling, the string object can be placed directly in the room such that the spatial extent of the string is represented directly:
<video poster="" title="" controls="controls" style="" width="640" height="">
	<source src="https://dl.dropboxusercontent.com/s/s16c6zlb624kv1b/animateStringInRoom.mp4?dl=0" />Your browser does not support this video format.
</video>



### Connection Matrix

<img src="BlockDiagram.png" width="600"/>

<strong>**Figure 1:**</strong> State-space description of a 1D string in a 2D room. The connection matrix $\mathbf{T}$ describes the modal connection between the string modes and the room modes. 

The following animation demonstrates the dependency of the connection matrix $\mathbf{T}$ on the spatial position of the string. The string position is rotated in each frame (while the absolute position in the room is similar to the animation above). The top right plot depicts the transfer function of the string (blue) and the resulting transfer function in the room at a pickup position (red):

<video poster="" title="" controls="controls" style="" width="640" height="">
	<source src="https://dl.dropboxusercontent.com/s/xrcp0m0jcc0t2nd/animateStringInRoom_rotation.mp4?dl=0" />Your browser does not support this video format.
</video>




### Audio Examples

We present various sound examples of a string in a room. First, the basic sound examples for string only, point in a room and string in a room with the same configuration as in the animations above.


<div class="player">
  <p>
      Sound example with various configuration.
  </p>
  <ts-track title="Only String" data-img="">
      <ts-source src="https://dl.dropboxusercontent.com/s/cvetl93gijsx0zr/stringOnly.wav?dl=0" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Point in a Room" data-img="">
      <ts-source src="https://dl.dropboxusercontent.com/s/6og8gq9543smjho/pointInRoom.wav?dl=0" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="String in a Room" data-img="">
      <ts-source src="https://dl.dropboxusercontent.com/s/dzd4cbq0o1yul9x/stringInRoom.wav?dl=0" type="audio/mpeg"></ts-source>
  </ts-track>
</div>


The following audio examples varies the position of the string in the room.



<div class="player">
  <p>
      Sound example with string configuration.
  </p>
  <img data-style="width: 100%; margin: auto;" class="seekable" src="">
  <ts-track title="Position 1" data-img="soundPlot_string_1.jpg">
      <ts-source src="stringInRoom_1.mp3" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Position 2" data-img="soundPlot_string_2.jpg">
      <ts-source src="stringInRoom_2.mp3" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Position 3" data-img="soundPlot_string_3.jpg">
      <ts-source src="stringInRoom_3.mp3" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Position 4" data-img="soundPlot_string_4.jpg">
      <ts-source src="stringInRoom_4.mp3" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Position 5" data-img="soundPlot_string_5.jpg">
      <ts-source src="stringInRoom_5.mp3" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Position 6" data-img="soundPlot_string_6.jpg">
      <ts-source src="stringInRoom_6.mp3" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Position 7" data-img="soundPlot_string_7.jpg">
      <ts-source src="stringInRoom_7.mp3" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Position 8" data-img="soundPlot_string_8.jpg">
      <ts-source src="stringInRoom_8.mp3" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Position 9" data-img="soundPlot_string_9.jpg">
      <ts-source src="stringInRoom_9.mp3" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Position 10" data-img="soundPlot_string_10.jpg">
      <ts-source src="stringInRoom_10.mp3" type="audio/mpeg"></ts-source>
  </ts-track>
</div>



The following audio examples varies the position of the receiver in the room.



<div class="player">
  <p>
      Sound example with receiver configuration.
  </p>
  <img data-style="width: 100%; margin: auto;" class="seekable" src="">
  <ts-track title="Position 11" data-img="soundPlot_string_11.jpg">
      <ts-source src="stringInRoom_11.mp3" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Position 12" data-img="soundPlot_string_12.jpg">
      <ts-source src="stringInRoom_12.mp3" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Position 13" data-img="soundPlot_string_13.jpg">
      <ts-source src="stringInRoom_13.mp3" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Position 14" data-img="soundPlot_string_14.jpg">
      <ts-source src="stringInRoom_14.mp3" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Position 15" data-img="soundPlot_string_15.jpg">
      <ts-source src="stringInRoom_15.mp3" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Position 16" data-img="soundPlot_string_16.jpg">
      <ts-source src="stringInRoom_16.mp3" type="audio/mpeg"></ts-source>
  </ts-track>
  <ts-track title="Position 17" data-img="soundPlot_string_17.jpg">
      <ts-source src="stringInRoom_17.mp3" type="audio/mpeg"></ts-source>
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