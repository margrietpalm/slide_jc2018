<img src="images/title.png" width="100%"/>


Motivation
------------------------------------------------------------
* Genotypic divergence and phenotypic convergence: "Multiple biopsies from the same tumor display distinct genetic profiles and yet are phenotypically similar"
* Consequence of evolution: selection of clones that survive in the TME
* TME is temporally and spatially heterogeneous
* Tumor progression and treatment results may be predicted based on phenotypic information alone.
  * circumvent much of the complexity observed at molecular scales and instead examine the functional outcome of mutation (be it genetic or epigenetic)
  * Focus on metabolic phenotype
    * tumors are known to be metabolically very different from normal tissue
    * metabolism contributes significantly to tumor progression.


Aim
-----------------
* Predict tumor progression based in context of metabolism and a heterogeneous TME
* Predict the effect of treatment strategies

Our intention here is to examine this work in light of the lens of metabolic and microenvironmental heterogeneity by reproducing observation and suggesting novel interpretation and treatment strategies. The focus of the work is on acid-mediated invasion, wherein tumor cells that have abnormally high glycolytic capacity acidify the local environment, causing the surrounding tissue to degrade and allow for tumor growth.


Model - overview
--------------------------
* Cellular automaton is a grid of pixels
* Each pixel represents a single cell
* Each cell has a metabolic state based on the metabolic model
* Glucose, oxygen, and H$^+$ diffuse over the domain


Model - metabolism
-----------------------------------------
<img src="images/metabolism_model_v2.png" width="100%" />
* Oxygen uptake determined by local oxygen concentration
* Glucose uptake is determined by ATP demand ($P \_
  \text{G}$)
* ATP production is determined by oxygen and glucose take up
* H$^+$ production depends on the amount of glycolysis
* New blood vessels are added inhypoxic areas


Model - cell decision process
-------------------------------------
<img src="images/fig1.png" width="50%" />


Model - variation and selection
-----------------------------------
<img src="images/fig2.png" width="50%" />


Untreated tumor progression
---------------------------------

<video width="1200" controls loop autoplay>
<source src="movies/movie1.mp4" type="video/mp4">
</video>

<div style="font-size: .55em; text-align: center; margin-top:-10px">white = blood vessel; black = empty space; dark gray = necrosis; medium gray = normal tissue;</div>

**Tumors acquire acid resistance followed by glycolytic capacity**



Caption
-----------------------------------------------
<div style="position:absolute;background: white;width:100%;height:600px">
<img src="images/placeholder.svg" width="100%"/>
<div style="font-size: .5em; text-align: center; margin-bottom: 20px">I made this myself</div>
</div>


Side-by-Side
--------------------
<div style="position:relative; width:100%;  margin-left: auto; margin-right: auto; text-align: center; margin-top: 30px" >
  <div style="position:absolute;background: white;width:100%;height:400px">
  <img src="images/placeholder.svg" height="300px"/>
  <p>1</p>
  </div>
  <div class="fragment" style="position:absolute;width:100%;background: white;height:400px">
  <img src="images/placeholder.svg" height="300px"/>
  <p>2</p>
  </div>  
</div>


Math without mathjax
--------------------------------------------------------
- Use unicode: 3&#x22C5;10&#x2075;
