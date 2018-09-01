<img src="images/title.png" width="100%"/>

TLDR: Computational model of tumor progression gives insight in how tumors progress and respond to treatment.



Genotypic divergence and phenotypic convergence
------------------------------------------------------------
<blockquote style="display:block; width:100%; font-size:.8em">
Multiple biopsies from the same tumor display distinct genetic profiles and yet are phenotypically similar
</blockquote>

* Consequence of evolution:
  * cells are in the same TME
  * selection of clones that survive in that TME
* Interaction between TME and evolution determines tumor progression


Spatial heterogeneity in the TME
----------------------------------------
* TME is temporally and spatially heterogeneous
* Different cell types and tissues:
  * normal cells
  * blood vessels
  * tumor cells
* Spatial heterogeneity and metabolism:
  * Oxygen and glucose levels vary due to uptake
  * H$^+$ level varies due to glycolysis



Model - overview
--------------------------
* Cellular automaton represents tissue with tumor
* Each pixel is a single cell
* Each cell has a metabolic state based on the metabolic model
* Glucose, oxygen, and H$^+$ diffuse over the domain


Model - cellular automaton
------------------------------
  <div style="display:flex; justify-content:center;font-size:.9em;">
    <div style="width:1200px">
    <ul>
    <li> Spatial domain (=tumor) is represented by a grid of pixels</li>
    <li> Every time step each pixel is updated based:</li>
      <ul>
      <li> its own state </li>
      <li> the state of its neighbors </li>
      </ul>
    </ul>
    </div>
    <div style="width:500px">
      <img src="images/game_of_life.gif"/>
    </div>
  </div>


Model - update scheme
-----------------------------
<img src="images/fig1.png" width="50%" />


Model - metabolism
-----------------------------------------
<img src="images/metabolism_model_v2.png" width="100%" />
* Oxygen uptake determined by local oxygen concentration
* Glucose uptake is determined by ATP demand ($P \_
  \text{G}$)
* ATP production is determined by oxygen and glucose take up
* H$^+$ production depends on the amount of glycolysis
* New blood vessels are added inhypoxic areas


Model - evolution
-----------------------------
<div style="display:flex; justify-content:center;font-size:.9em;">
  <div width="400px">  
  <ul>
    <li>Evolving parameters</li>
    <ul>
      <li> excess glucose consumpion = glycolysis </li>
      <li> acid resistance </li>
    </ul>
    <li> Values are tranfsered to dauther cells, with some noise </li>
    </ul>
  </div>
  <div width="800pix">
  <img src="images/fig1.png" width="100%" />
  </div>
</div>



Results - 2 modes of tumor growth
---------------------------------

<video width="1200" controls loop autoplay>
<source src="movies/movie1.mp4" type="video/mp4">
</video>

<div style="font-size: .55em; text-align: center; margin-top:-10px">
white = blood vessel; black = empty space; dark gray = necrosis; medium gray = normal tissue;
<br>
green = normal tumor cell; blue = acid resistant; mangenta = glycolytic;
</div>

1. Homeostatic growth limited by available space
2. Invasive growth when tumor induces cell death in normal tissue


Results - Invasion
------------------
1. Shift to acid resistance during short periods of hypoxia
2. Hypoxic core leads to reliance on glycolysis
3. Glycolytic cells develop but cannot leave the core
4. Glycolytic cells reach boundary and start Invasion


pH buffering therapy
---------------------------

<video width="1200" controls loop autoplay>
<source src="movies/movie2.mp4" type="video/mp4">
</video>


pH buffering therapy
---------------------------
* application of systemic pH buffers to mice can prevent or slow down tumor development and metastatic growth
* treatment before invasive state stops cell from breaking the buffers
* treatment after does not help


Anti-angiogenic therapy
-----------------------------

<video width="600px" controls loop autoplay>
<source src="movies/movie3.mp4" type="video/mp4">
</video>


Anti-angiogenic therapy
-----------------------------
* blood vessels are not added
* treatment increases selection in favor of aggressive cells


Cytotoxic therapy
--------------------

<video width="1200" controls loop autoplay>
<source src="movies/movie4.mp4" type="video/mp4">
</video>


Cytotoxic therapy
--------------------  
* toxins are delivered by the blood -> spatial e  ffect s



&#x1F44D; and &#x1F44E;
---------------------------
<div style="display:flex; justify-content:center;font-size:.9em; text-align:left">
  <div width="500px">
  &#x1F44D;
  <ul>
    <li> mechanistic insight in tumor progression </li>
    <li> mechanistic insight in treatment effects </li>
    <li> focus on phenotype </li>
  </ul>
  </div>
  <div width="500px">
  &#x1F44E;
  <ul>
    <li> treatments are over-simplefied </li>
    <li> no quantitative analysis </li>
    <li> 2D model that does not consider mechanics </li>
  </div>
</div>
