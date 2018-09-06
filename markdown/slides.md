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
* New blood vessels are added in hypoxic areas


Model - evolution
-----------------------------
<div style="display:flex; justify-content:center;font-size:.9em;">
  <div width="400px">  
  <ul>
    <li>Evolving parameters</li>
    <ul>
      <li> excess glucose consumption = glycolysis </li>
      <li> acid resistance </li>
    </ul>
    <li> Values are transferred to daughter cells, with some noise </li>
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
green = normal tumor cell; blue = acid resistant; magenta = glycolytic;
</div>

1. Homeostatic growth limited by available space
2. Invasive growth when tumor induces cell death in normal tissue


Results - Invasion
------------------
1. Shift to acid resistance during short periods of hypoxia
2. Hypoxic core, with acid resistant cells, leads to need for glycolysis
3. Glycolytic cells develop but cannot leave the core
4. Glycolytic cells reach boundary and start Invasion

<div style="display: flex; flex-direction: row">
  <div width="25%"><img src="images/fig3a.jpg"></div>
  <div><img src="images/fig3c.jpg"></div>
  <div><img src="images/fig3e.jpg"></div>
  <div><img src="images/fig3g.jpg"></div>
</div>

<div style="font-size: .55em; text-align: center; margin-top:-10px">
white = blood vessel; black = empty space; dark gray = necrosis; medium gray = normal tissue;
<br>
green = normal tumor cell; blue = acid resistant; magenta = glycolytic;
</div>


pH buffering therapy
---------------------------
<div style="display: flex; flex-direction: row; font-size: .8em; text-align: center">
  <div style="min-width:300px">untreated</div>
  <div style="min-width:300px">early treatment</div>
  <div style="min-width:300px">late treatment</div>
</div>

<video width="1200" controls loop autoplay>
<source src="movies/movie2.mp4" type="video/mp4">
</video>

Note:
* Early treatment blocks development of acid resistant cells and thus no invasion
* Fits with observation that early treated mice to not develop metastasis
* While late treatment may not block tumor development, may prevent metastasis cascade


Anti-angiogenic therapy
-----------------------------
* Long standing hypothesis: blocking angiogenesis blocks tumor growth
* Trails are generally not successful
  * Same treatments do block angiogenesis
* Blocking angiogenesis causes hypoxia and reduces pH


Anti-angiogenic therapy
-----------------------------
<video width="600px" controls loop autoplay>
<source src="movies/movie3.mp4" type="video/mp4">
</video>


Cytotoxic therapy
--------------------
* Drug reached tumor via diffusion
* Most aggressive cells develop in the core
  * Can drugs reach these cells?
  * Do drugs free those cells?

<div style="margin-top: 50px; display: flex; flex-direction: row; font-size: .8em; text-align: center">
  <div style="min-width:300px">untreated</div>
  <div style="min-width:300px">early treatment</div>
  <div style="min-width:300px">late treatment</div>
</div>

<video width="1200" controls loop autoplay>
<source src="movies/movie4.mp4" type="video/mp4">
</video>


Cytotoxic therapy
--------------------  
<img src="images/fig6.jpg"/>
* Early treatment: reduce initial tumor size and limits invasion
* Late treatment: buffer of metabolically benign cells is killed



Main conclusions
----------------------
* Tumors become invasive when the aggressive cells that develop in the core can escape
* Late treatments may help aggressive cells escape


What I really like &#x1F603;
-------------------------------
* Model gives mechanistic insights in tumor progression and treatments
* Model focuses on phenotype instead of genotype
  * phenotype to genotype translation is often unknown
* Model highlights the importance of the tumor environment


What could be better &#x1F620;
--------------------------------
* There is no cell migration in this invasion model
* No mechanics and no ECM
* Diffusion of nutrients / treatments is not affected by spatial heterogeneity
* No quantitative analysis of the model or parameter sensitivity analysis
* Not enough information to reproduce the model
  * Methods are not fully described
  * Code not published &#x1F62D;



How about combination therapy?
---------------------------------------
DIY: Cancer Crusade game for Android and iOS (http://cancercrusadegame.com/)

<div style="margin-top: 50px; display: flex; flex-direction: row; font-size: .8em; text-align: center">
  <div width="25%"><img src="images/Slide1.png"></div>
  <div><img src="images/Slide2.png"></div>
  <div><img src="images/Slide5.png"></div>
  <div><img src="images/Slide6.png"></div>
</div>
