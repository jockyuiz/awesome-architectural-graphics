# Awesome-Architectural-Graphics

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

A collection of papers about computer graphics research projects in the last few years that involved potential architectural applications. Mainly focus on architectural geometry, vector fields, shape analysis, inverse CAD design, etc.

> Feel free to create a PR or an issue.

![examples](http://www-labs.iro.umontreal.ca/~bmpix/curve_networks/images/teaser_web.png)

**Outlines**

- [1. Design Synthesis](#0-Creative-ideas-&-design)
  - [1) 2D Floorplan synthesis](#1-semantic-concept-to-sketch)
  - [2) 3D Shape generation](#2-photo-to-sketch)
- [2. (Inverse) CAD Modeling](#1-datasets)
  - [1) Sketch-to-CAD](#1-semantic-concept-to-sketch)
  - [2) Photo-to-CAD](#2-photo-to-sketch)
  - [3) Text/Attribute-to-CAD](#3-textattribute-to-sketch)
  - [4) Procedural Modeling](#4-3d-shape-to-sketch)
- [3. Geometry Optimization](#2-sketch-synthesis-approaches)(Topology Optimization Excluded)
  - [1) Fabrication-oriented Geometry](#1-semantic-concept-to-sketch)
  - [2) Structure-oriented Geometry](#2-photo-to-sketch)
  - [3) Deployment-oriented Geometry](#3-textattribute-to-sketch)
  - [4) Curve/Ribbon/Crease](#4-3d-shape-to-sketch)
- [4. Directional Field](#3-vector-graphics-generation)  
- [5. Design Space](#3-vector-graphics-generation)

---


## 1. Creative ideas & design
Here `Vector strokes` means having *svg* data. `With photos` means having the photo-sketch paired data.

<table>
  <tr>
    <td><strong>Level</strong></td>
    <td><strong>Dataset</strong></td>
    <td><strong>Source</strong></td>
    <td><strong>Vector strokes</strong></td>
    <td><strong>With photos</strong></td>
    <td><strong>Notes</strong></td>
  </tr>
  <tr>
    <td rowspan="3"><strong>Characters</strong></td>
    <td> <a href="https://github.com/brendenlake/omniglot/">Omniglot</a> </td> 
    <td> </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> Alphabets characters </td>
  </tr>
  <tr>
    <td> <a href="http://kanjivg.tagaini.net/">KanjiVG</a> </td> 
    <td> </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> Chinese characters </td>
  </tr>
  <tr>
    <td> <a href="https://github.com/rois-codh/kmnist">Kuzushiji</a> </td> 
    <td> </td> 
    <td> :x: </td> 
    <td> :x: </td> 
    <td> Japanese characters </td>
  </tr>
  <tr>
    <td rowspan="8"><strong>Instance-level</strong></td>
    <td> <a href="http://cybertron.cg.tu-berlin.de/eitz/projects/classifysketch/">TU-Berlin</a> </td> 
    <td> SIGGRAPH 2012 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> Multi-category hand sketches </td>
  </tr>
  <tr>
    <td> <a href="http://sketchy.eye.gatech.edu/">Sketchy</a> </td> 
    <td> SIGGRAPH 2016 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Multi-category photo-sketch paired </td>
  </tr>
  <tr>
    <td> <a href="https://quickdraw.withgoogle.com/data">QuickDraw</a> </td> 
    <td> ICLR 2018 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> Multi-category hand sketches </td>
  </tr>
  <tr>
    <td> <a href="http://www.eecs.qmul.ac.uk/~qian/Project_cvpr16.html">QMUL-Shoe-Chair-V2</a> </td> 
    <td> CVPR 2016 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Only two categories </td>
  </tr>
  <tr>
    <td> <a href="https://github.com/KeLi-SketchX/SketchX-PRIS-Dataset">Sketch Perceptual Grouping (SPG)</a> </td> 
    <td> ECCV 2018 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> With part-level semantic segmentation information </td>
  </tr>
  <tr>
    <td> <a href="https://facex.idvxlab.com/">FaceX</a> </td> 
    <td> AAAI 2019 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> Labeled facial sketches </td>  
  </tr>
  <tr>
    <td> <a href="https://github.com/facebookresearch/DoodlerGAN">Creative Sketch</a> </td> 
    <td> ICLR 2021 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> With annotated part segmentation </td>  
  </tr>
  <tr>
    <td> <a href="https://github.com/HaohanWang/ImageNet-Sketch">ImageNet-Sketch</a> </td> 
    <td> NeurIPS 2019 </td> 
    <td> :x: </td> 
    <td> :x: </td> 
    <td> 50 images for each of the 1000 ImageNet classes </td>  
  </tr>
  <tr>
    <td rowspan="5"><strong>Scene-level</strong></td>
    <td> <a href="https://sketchyscene.github.io/SketchyScene/">SketchyScene</a> </td> 
    <td> ECCV 2018 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> With semantic/instance segmentation information </td>  
  </tr>
  <tr>
    <td> <a href="http://projects.csail.mit.edu/cmplaces/">CMPlaces</a> </td> 
    <td> TPAMI 2018 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Cross-modal scene dataset </td>  
  </tr>
  <tr>
    <td> <a href="http://sweb.cityu.edu.hk/hongbofu/doc/context_based_sketch_classification_Expressive2018.pdf">Context-Skecth</a> </td> 
    <td> Expressive 2018 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Context-based scene sketches for co-classification </td>  
  </tr>
  <tr>
    <td> <a href="https://sysu-imsl.github.io/EdgeGAN/index.html">SketchyCOCO</a> </td> 
    <td> CVPR 2020 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Scene sketch, segmentation and normal images </td>  
  </tr>
  <tr>
    <td> <a href="http://www.pinakinathc.me/fscoco/">FS-COCO</a> </td> 
    <td> ECCV 2022 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Scene sketches with text description </td>  
  </tr>
  <tr>
    <td rowspan="2"><strong>Drawing from photos</strong></td>
    <td> <a href="http://www.cs.cmu.edu/~mengtial/proj/sketch/">Photo-Sketching</a> </td> 
    <td> WACV 2019 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :heavy_check_mark: </td> 
    <td> ScenePhoto-sketch paired </td>
  </tr>
  <tr>
    <td> <a href="https://github.com/zachzeyuwang/tracing-vs-freehand">Tracing-vs-Freehand</a> </td> 
    <td> SIGGRAPH 2021 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Tracings and freehand drawings of images </td>  
  </tr>
  <tr>
    <td rowspan="1"><strong>Portrait</strong></td>
    <td> <a href="https://github.com/yiranran/APDrawingGAN">APDrawing</a> </td> 
    <td> CVPR 2019 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Portrait-sketch paired </td>
  </tr>
  <tr>
    <td rowspan="2"><strong>Rough sketch</strong></td>
    <td> <a href="https://esslab.jp/~ess/en/data/davincidataset/">Da Vinci</a> </td> 
    <td> CGI 2018 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Line drawing restoration dataset </td>
  </tr>
  <tr>
    <td> <a href="https://cragl.cs.gmu.edu/sketchbench/">Rough Sketch Benchmark</a> </td> 
    <td> SIGGRAPH Asia 2020 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Rough and clean sketch pairs (only for evaluation) </td>  
  </tr>
  <tr>
    <td rowspan="5"><strong>CAD</strong></td>
    <td> <a href="https://gfx.cs.princeton.edu/proj/ld3d/">ld3d</a> </td> 
    <td> SIGGRAPH 2008 </td> 
    <td> :x: </td> 
    <td> :x: </td> 
    <td> Line Drawings of 3D Shapes </td>
  </tr>
  <tr>
    <td> <a href="https://ns.inria.fr/d3/OpenSketch/">OpenSketch</a> </td> 
    <td> SIGGRAPH Asia 2019 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> Product Design Sketches </td>
  </tr>
  <tr>
    <td> <a href="https://github.com/PrincetonLIPS/SketchGraphs">SketchGraphs</a> </td> 
    <td> ICML 2020 Workshop </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> Sketches extracted from real-world CAD models </td>  
  </tr>
  <tr>
    <td> <a href="https://github.com/AutodeskAILab/Fusion360GalleryDataset">Fusion 360 Gallery</a> </td> 
    <td> SIGGRAPH 2021 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> For 'sketch and extrude' designs </td>  
  </tr>
  <tr>
    <td> <a href="https://floorplancad.github.io/">FloorPlanCAD</a> </td> 
    <td> ICCV 2021 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> With instance and semantic annotations </td>  
  </tr>
  
</table>



## 2. Architectural Geometry 

### 1) Curve network


<table>
  <tr>
    <td><strong>Level</strong></td>
    <td><strong>Paper</strong></td>
    <td><strong>Source</strong></td>
    <td><strong>Code/Project Link</strong></td>
  </tr>
  <tr>
    <td rowspan="8"><strong>Curve-study</strong></td>
    <td> <a href="http://www-labs.iro.umontreal.ca/~bmpix/curve_networks/files/curve_networks.pdf">Stability-Aware Simplification of Curve Networks</a> </td> 
    <td> SIGGRAPH 2022 </td> 
    <td> 
      <a href="https://github.com/wwwnev/Stability-Aware-Simplification-of-Curve-Networks">[Code]</a> 
      <a href="http://www-labs.iro.umontreal.ca/~bmpix/curve_networks/">[Project]</a> 
      <a href="https://siggraph2022.hubb.me/fe/schedule-builder/sessions/937885">[Presentation]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://lgg.epfl.ch/publications/2021/Weaving/paper.pdf">3D Weaving with Curved Ribbons</a> </td> 
    <td> SIGGRAPH 2021 </td> 
    <td> 
      <a href="https://lgg.epfl.ch/publications/2021/Weaving/index.php">[Project]</a> 
      <a href="https://lgg.epfl.ch/publications/2021/Weaving/vis_app/index.html">[Web Demo]</a>
    </td>
  </tr>
  <tr>
    <td> <a href="https://research-explorer.app.ist.ac.at/download/9817/10150/elastic-curves-paper.pdf">THE DESIGN SPACE OF PLANE ELASTIC CURVES</a> </td> 
    <td> SIGGRAPH 2021 </td> 
    <td> 
      <a href="http://visualcomputing.ist.ac.at/publications/2021/TDSOPEC/">[Project]</a> 
      <a href="http://pub.ist.ac.at/~chafner/ElasticCurves2021/elastic-curves-code.zip">[Code]</a>
    </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/pdf/1901.03427.pdf">Stroke-based sketched symbol reconstruction and segmentation (stroke-rnn)</a> </td> 
    <td> </td> 
    <td> </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/abs/2007.02190">BézierSketch: A generative model for scalable vector sketches</a> </td> 
    <td> ECCV 2020 </td> 
    <td>  </td>
  </tr>
  <tr>
    <td> <a href="http://sketchx.ai/pixelor">Pixelor: A Competitive Sketching AI Agent. So you think you can beat me?</a> </td> 
    <td> SIGGRAPH Asia 2020 </td> 
    <td> 
      <a href="http://sketchx.ai/pixelor">[Project]</a> 
      <a href="https://github.com/dasayan05/neuralsort-siggraph">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/abs/2011.10039">Creative Sketch Generation</a> </td> 
    <td> ICLR 2021 </td> 
    <td> 
      <a href="http://doodlergan.cloudcv.org/">[Project]</a> 
      <a href="https://github.com/facebookresearch/DoodlerGAN">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/abs/2105.02769">Computer-Aided Design as Language</a> </td> 
    <td> arxiv 2105 </td> 
    <td> 
    </td>
  </tr>
  
</table>

---

### 2) Discrete nets/meshes

- vector image generation

<table>
  <tr>
    <td><strong>Data type</strong></td>
    <td><strong>Paper</strong></td>
    <td><strong>Source</strong></td>
    <td><strong>Code/Project Link</strong></td>
  </tr>
  <tr>
    <td rowspan="3"><strong>Facial</strong></td>
    <td> <a href="https://dl.acm.org/citation.cfm?id=2461964">Style and abstraction in portrait sketching</a> </td> 
    <td> TOG 2013 </td> 
    <td>
    </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/abs/2005.05526">Making Robots Draw A Vivid Portrait In Two Minutes</a> </td> 
    <td> IROS 2020 </td> 
    <td> 
      <a href="https://github.com/Ricelll/AiSketcher">[Code]</a> 
      <a href="https://ricelll.github.io/AiSketcher/">[Project]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/abs/1912.05099">RoboCoDraw: Robotic Avatar Drawing with GAN-based Style Transfer and Time-efficient Path Optimization</a> </td> 
    <td> AAAI 2020 </td> 
    <td> 
      <a href="https://github.com/Psyche-mia/Avatar-GAN">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td rowspan="4"><strong>Instance-level</strong></td>
    <td> <a href="https://link.springer.com/content/pdf/10.1007%2Fs11263-016-0963-9.pdf">Free-Hand Sketch Synthesis with Deformable Stroke Models</a> </td> 
    <td> IJCV 2017 </td> 
    <td>
      <a href="https://panly099.github.io/skSyn.html">[Project]</a> 
      <a href="https://github.com/panly099/sketchSynthesis">[code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="http://openaccess.thecvf.com/content_cvpr_2018/papers/Song_Learning_to_Sketch_CVPR_2018_paper.pdf">Learning to Sketch with Shortcut Cycle Consistency</a> </td> 
    <td> CVPR 2018 </td> 
    <td> <a href="https://github.com/seindlut/deep_p2s">[Code1]</a> <a href="https://github.com/MarkMoHR/sketch-photo2seq">[Code2]</a> </td>
  </tr>
  <tr>
    <td> <a href="http://openaccess.thecvf.com/content_cvpr_2018/papers/Muhammad_Learning_Deep_Sketch_CVPR_2018_paper.pdf">Learning Deep Sketch Abstraction</a> </td> 
    <td> CVPR 2018 </td> 
    <td>  </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/abs/2202.05822">CLIPasso: Semantically-Aware Object Sketching</a> </td> 
    <td> SIGGRAPH 2022 </td> 
    <td> 
      <a href="https://clipasso.github.io/clipasso/">[Project]</a> 
      <a href="https://github.com/yael-vinker/CLIPasso">[Code]</a>
    </td>
  </tr>
  <tr>
    <td rowspan="1"><strong>Technical Drawings</strong></td>
    <td> <a href="https://arxiv.org/abs/2003.05471">Deep Vectorization of Technical Drawings</a> </td> 
    <td> ECCV 2020 </td> 
    <td>
      <a href="http://adase.group/3ddl/projects/vectorization/">[Project]</a> 
      <a href="https://github.com/Vahe1994/Deep-Vectorization-of-Technical-Drawings">[code]</a> 
    </td>
  </tr>
  <tr>
    <td rowspan="1"><strong>Scene-level</strong></td>
    <td> <a href="https://arxiv.org/abs/2012.09004">Sketch Generation with Drawing Process Guided by Vector Flow and Grayscale</a> </td> 
    <td> AAAI 2021 </td> 
    <td>
      <a href="https://github.com/TZYSJTU/Sketch-Generation-with-Drawing-Process-Guided-by-Vector-Flow-and-Grayscale">[Code]</a> 
    </td>
  </tr>
</table>


- pixelwise image generation

<table>
  <tr>
    <td><strong>Level</strong></td>
    <td><strong>Paper</strong></td>
    <td><strong>Source</strong></td>
    <td><strong>Code/Project Link</strong></td>
  </tr>
  <tr>
    <td rowspan="5"><strong>Facial</strong></td>
    <td> <a href="https://github.com/vijishmadhavan/ArtLine">ArtLine</a> </td> 
    <td> Online demo </td> 
    <td> 
      <a href="https://github.com/vijishmadhavan/ArtLine">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="http://openaccess.thecvf.com/content_CVPR_2019/papers/Yi_APDrawingGAN_Generating_Artistic_Portrait_Drawings_From_Face_Photos_With_Hierarchical_CVPR_2019_paper.pdf">APDrawingGAN: Generating Artistic Portrait Drawings from Face Photos with Hierarchical GANs</a> </td> 
    <td> CVPR 2019 </td> 
    <td> 
      <a href="https://github.com/yiranran/APDrawingGAN">[Code]</a> 
      <a href="https://face.lol/">[Demo]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://openaccess.thecvf.com/content_CVPR_2020/papers/Yi_Unpaired_Portrait_Drawing_Generation_via_Asymmetric_Cycle_Mapping_CVPR_2020_paper.pdf">Unpaired Portrait Drawing Generation via Asymmetric Cycle Mapping</a> </td> 
    <td> CVPR 2020 </td> 
    <td> 
      <a href="https://github.com/yiranran/Unpaired-Portrait-Drawing">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://ieeexplore.ieee.org/document/9069416">Line Drawings for Face Portraits From Photos Using Global and Local Structure Based GANs</a> </td> 
    <td> TPAMI 2020 </td> 
    <td> 
      <a href="https://github.com/yiranran/APDrawingGAN2">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://ieeexplore.ieee.org/abstract/document/9699090">Quality Metric Guided Portrait Line Drawing Generation from Unpaired Training Data</a> </td> 
    <td> TPAMI 2022 </td> 
    <td> 
      <a href="https://github.com/yiranran/QMUPD">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td rowspan="3"><strong>Instance-level</strong></td>
    <td> <a href="http://openaccess.thecvf.com/content_ECCV_2018/papers/Kaiyue_Pang_Deep_Factorised_Inverse-Sketching_ECCV_2018_paper.pdf">Deep Factorised Inverse-Sketching</a> </td> 
    <td> ECCV 2018 </td> 
    <td> </td>
  </tr>
  <tr>
    <td> <a href="https://www.spiedigitallibrary.org/journals/Journal-of-Electronic-Imaging/volume-27/issue-6/063006/Making-better-use-of-edges-for-sketch-generation/10.1117/1.JEI.27.6.063006.short?SSO=1">Making better use of edges for sketch generation</a> </td> 
    <td> JEI 2018 </td> 
    <td> </td>
  </tr>
  <tr>
    <td> <a href="http://openaccess.thecvf.com/content_WACV_2020/papers/Kampelmuhler_Synthesizing_human-like_sketches_from_natural_images_using_a_conditional_convolutional_WACV_2020_paper.pdf">Synthesizing human-like sketches from natural images using a conditional convolutional decoder</a> </td> 
    <td> WACV 2020 </td> 
    <td> 
      <a href="https://github.com/kampelmuehler/synthesizing_human_like_sketches">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td rowspan="2"><strong>Scene-level</strong></td>
    <td> <a href="https://arxiv.org/pdf/1901.00542.pdf">Photo-Sketching: Inferring Contour Drawings from Images</a> </td> 
    <td> WACV 2019 </td> 
    <td>
      <a href="https://github.com/mtli/PhotoSketch">[Code]</a> 
      <a href="http://www.cs.cmu.edu/~mengtial/proj/sketch/">[Project]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://carolineec.github.io/informative_drawings/">Learning to generate line drawings that convey geometry and semantics</a> </td> 
    <td> CVPR 2022 </td> 
    <td> 
      <a href="https://github.com/carolineec/informative-drawings">[Code]</a> 
      <a href="https://carolineec.github.io/informative_drawings/">[Project]</a> 
    </td>
  </tr>
</table>

---

### 3) Deployable system

| Level | Paper | Source | Code/Project Link |
| --- | --- | --- | --- |
| **Facial** | [Text2Sketch: Learning Face Sketch from Facial Attribute Text](https://ieeexplore.ieee.org/abstract/document/8451236) | ICIP 2018 |  |
| **Scene-level** | [Sketchforme: Composing Sketched Scenes from Text Descriptions for Interactive Applications](https://arxiv.org/pdf/1904.04399.pdf) | UIST 2019 |  |
| **Scene-level** | [Scones: Towards Conversational Authoring of Sketches](http://people.eecs.berkeley.edu/~eschoop/docs/scones.pdf) | IUI 2020 |  |
| **Arbitrary** | [CLIPDraw: Exploring Text-to-Drawing Synthesis through Language-Image Encoders](https://arxiv.org/abs/2106.14843) | arxiv 2106 | [[code]](https://colab.research.google.com/github/kvfrans/clipdraw/blob/main/clipdraw.ipynb) |
| **Arbitrary** | [Modern Evolution Strategies for Creativity: Fitting Concrete Images and Abstract Concepts](https://arxiv.org/abs/2109.08857) | arxiv 2109 | [[code]](https://github.com/google/brain-tokyo-workshop) [[project]](https://es-clip.github.io/) |

---

### 4) 3D shape-to-sketch

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [DeepShapeSketch : Generating hand drawing sketches from 3D objects](https://shizhezhou.github.io/projects/DeepFreeHandSke2019/deepFreehandSke2019.pdf) | IJCNN 2019 |  |
| [Neural Contours: Learning to Draw Lines from 3D Shapes](https://people.cs.umass.edu/~dliu/papers/NeuralContours.pdf) | CVPR 2020 | [[project]](https://people.cs.umass.edu/~dliu/projects/NeuralContours/) [[code]](https://github.com/DifanLiu/NeuralContours) |
| [Cloud2Curve: Generation and Vectorization of Parametric Sketches](https://arxiv.org/abs/2103.15536) | CVPR 2021 | [[project]](https://ayandas.me/pubs/2021/03/01/pub-9.html) |
| [Neural Strokes: Stylized Line Drawing of 3D Shapes](https://openaccess.thecvf.com/content/ICCV2021/papers/Liu_Neural_Strokes_Stylized_Line_Drawing_of_3D_Shapes_ICCV_2021_paper.pdf) | ICCV 2021 | [[code]](https://github.com/DifanLiu/NeuralStrokes) |

---


### 5) Sketch(vector)-to-sketch(vector)


This means translating a disordered vector sketch into an ordered sequential sketch imitating human's drawing order. The appearance of the sequential sketch is exactly the **same** as the pixelwise one.


| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Animated Construction of Line Drawings](http://sweb.cityu.edu.hk/hongbofu/projects/animatedConstructionOfLineDrawings_SiggA11/animatedConstructionOfLineDrawings_SiggA11.pdf) | SIGGRAPH ASIA 2011 | [[Project]](http://sweb.cityu.edu.hk/hongbofu/projects/animatedConstructionOfLineDrawings_SiggA11/) [[code]](http://sweb.cityu.edu.hk/hongbofu/projects/animatedConstructionOfLineDrawings_SiggA11/Viewer_src.zip) [[Demo]](http://sweb.cityu.edu.hk/hongbofu/projects/animatedConstructionOfLineDrawings_SiggA11/Viewer.zip) |

---

### 6) Art-to-sketch

Here we list sketch synthesis based on other image types, like Manga, line art, rough sketch, etc.

- Line art

a) Datasets and benchmark

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [A Benchmark for Rough Sketch Cleanup](https://hal.archives-ouvertes.fr/hal-02939477/document) | SIGGRAPH Asia 2020 | [[Project]](https://cragl.cs.gmu.edu/sketchbench/)  [[Code]](https://github.com/Nauhcnay/A-Benchmark-for-Rough-Sketch-Cleanup) |

b) Vector-to-Vector

| Paper | Source | Code/Project Link | \*-based |
| --- | --- | --- | --- |
| [Closure-aware Sketch Simplification](http://www.cse.cuhk.edu.hk/~ttwong/papers/sketch/sketch.pdf) | SIGGRAPH Asia 2015 | [[Project]](https://www.cse.cuhk.edu.hk/~ttwong/papers/sketch/sketch.html) | Optimization |
| [StrokeAggregator: Consolidating Raw Sketches into Artist-Intended Curve Drawings](https://www.cs.ubc.ca/labs/imager/tr/2018/StrokeAggregator/StrokeAggregator_authorversion.pdf) | SIGGRAPH 2018 | [[Project]](https://www.cs.ubc.ca/labs/imager/tr/2018/StrokeAggregator/) | Optimization |
| [StrokeStrip: Joint Parameterization and Fitting of Stroke Clusters](https://www.davepagurek.com/programming/strokestrip/) | SIGGRAPH 2021 | [[Project]](https://www.davepagurek.com/programming/strokestrip/) [[code]](https://github.com/davepagurek/StrokeStrip) | Optimization |

c) Raster-to-Vector (a.k.a. Vectorization)

| Paper | Source | Code/Project Link | \*-based |
| --- | --- | --- | --- |
| [Topology-Driven Vectorization of Clean Line Drawings](https://cgl.ethz.ch/Downloads/Publications/Papers/2013/Nor13/Nor13.pdf) | TOG 2013 | | Optimization |
| [Fidelity vs. Simplicity: a Global Approach to Line Drawing Vectorization](https://www-sop.inria.fr/reves/Basilic/2016/FLB16/fidelity_simplicity.pdf) | SIGGRAPH 2016 | [[Project]](https://www-sop.inria.fr/reves/Basilic/2016/FLB16/) | Optimization |
| [A Delaunay triangulation based approach for cleaning rough sketches](https://ed.iitm.ac.in/~raman/agcl/sketchSMI.pdf) | C&G 2018 | [[Code]](https://github.com/amaldevp/RoughSketchSimplification) | Optimization |
| [Semantic Segmentation for Line Drawing Vectorization Using Neural Networks](http://www.byungsoo.me/project/vectornet/paper.pdf) | EG 2018 | [[project]](http://www.byungsoo.me/project/vectornet) [[code]](https://github.com/byungsook/vectornet) | Learning |
| [Deep Line Drawing Vectorization via Line Subdivision and Topology Reconstruction](https://www.researchgate.net/profile/Chu_Han8/publication/337249870_Deep_Line_Drawing_Vectorization_via_Line_Subdivision_and_Topology_Reconstruction/links/5f0fec43299bf1e548ba370f/Deep-Line-Drawing-Vectorization-via-Line-Subdivision-and-Topology-Reconstruction.pdf) | PG 2019 | | Learning |
| [Inertia-based Fast Vectorization of Line Drawings](https://www.researchgate.net/profile/Rafal_Scherer/publication/336936860_Inertia-based_Fast_Vectorization_of_Line_Drawings/links/5dbbc8ad299bf1a47b0721d1/Inertia-based-Fast-Vectorization-of-Line-Drawings.pdf) | PG 2019 | | Optimization |
| [Vectorization of Line Drawings via Polyvector Fields](https://dl.acm.org/doi/10.1145/3202661) | TOG 2019 | [[Code]](https://github.com/bmpix/PolyVectorization) | Optimization |
| [Integer-Grid Sketch Simplification and Vectorization](http://www-sop.inria.fr/reves/Basilic/2020/SBBB20/paper.pdf) | SGP 2020 | [[Project]](https://repo-sam.inria.fr/d3/grid-vectorization/) [[Code]](https://gitlab.inria.fr/D3/grid-vectorization/) | Optimization |
| [Deep Vectorization of Technical Drawings](https://arxiv.org/abs/2003.05471) | ECCV 2020 | [[project]](http://adase.group/3ddl/projects/vectorization/) [[code]](https://github.com/Vahe1994/Deep-Vectorization-of-Technical-Drawings) | Learning |
| [General Virtual Sketching Framework for Vector Line Art](https://esslab.jp/publications/HaoranSIGGRAPH2021.pdf) | SIGGRAPH 2021 | [[project]](https://markmohr.github.io/virtual_sketching/) [[code]](https://github.com/MarkMoHR/virtual_sketching) | Learning |
| [Keypoint-Driven Line Drawing Vectorization via PolyVector Flow](http://www-labs.iro.umontreal.ca/~bmpix/pdf/polyvector_flow.pdf) | SIGGRAPH Asia 2021 | [[project]](https://puhachov.xyz/publications/keypoint-driven-polyvector-flow/) | Learning + Optimization |
| [End-to-end Line Drawing Vectorization](https://www.aaai.org/AAAI22Papers/AAAI-52.LiuH.pdf) | AAAI 2022 |  | Learning |
| [Vectorizing Line Drawings of Arbitrary Thickness via Boundary-based Topology Reconstruction](https://onlinelibrary.wiley.com/doi/full/10.1111/cgf.14485) | CGF 2022 |  | Heuristic |


- Rough sketch simplification

| Paper | Source | Code/Project Link |
| --- | --- | --- | 
| [Learning to Simplify: Fully Convolutional Networks for Rough Sketch Cleanup](https://esslab.jp/publications/SimoSerraSIGGRAPH2016.pdf) | SIGGRAPH 2016 | [[Code]](https://github.com/bobbens/sketch_simplification) [[Project]](https://esslab.jp/~ess/en/research/sketch/) |
| [Mastering Sketching: Adversarial Augmentation for Structured Prediction](https://esslab.jp/~ess/publications/SimoSerraTOG2018.pdf) | SIGGRAPH 2018 | [[Code]](https://github.com/bobbens/sketch_simplification)  [[Project]](https://esslab.jp/~ess/en/research/sketch_master/) |
| [Real-Time Data-Driven Interactive Rough Sketch Inking](https://esslab.jp/~ess/publications/SimoSerraSIGGRAPH2018.pdf) | SIGGRAPH 2018 | [[Code]](https://github.com/bobbens/line_thinning) [[Project]](https://esslab.jp/~ess/en/research/inking/) |
| [Perceptual-aware Sketch Simplification Based on Integrated VGG Layers](https://ieeexplore.ieee.org/abstract/document/8771128/) | TVCG 2019 |  |

- Manga (Comics)

| Paper | Source | Code/Project Link |
| --- | --- | --- | 
| [Deep extraction of manga structural lines](https://dl.acm.org/citation.cfm?id=3073675) | SIGGRAPH 2017 | [[Code]](https://github.com/ljsabc/MangaLineExtraction) |
| [Manga Filling Style Conversion with Screentone Variational Autoencoder](https://www.cse.cuhk.edu.hk/~ttwong/papers/screenstyle/screenstyle.html) | SIGGRAPH Asia 2020 | [[Project]](https://www.cse.cuhk.edu.hk/~ttwong/papers/screenstyle/screenstyle.html) [[Code]](https://github.com/msxie92/ScreenStyle) |
| [Generating Manga from Illustrations via Mimicking Manga Workflow](https://openaccess.thecvf.com/content/CVPR2021/papers/Zhang_Generating_Manga_From_Illustrations_via_Mimicking_Manga_Creation_Workflow_CVPR_2021_paper.pdf) | CVPR 2021 | [[Project]](https://lllyasviel.github.io/MangaFilter/) [[Code]](https://github.com/lllyasviel/MangaFilter) |
| [MangaGAN: Unpaired Photo-to-Manga Translation Based on The Methodology of Manga Drawing](https://arxiv.org/abs/2004.10634) | AAAI 2021 | |
| [Vectorization of Raster Manga by Deep Reinforcement Learning](https://arxiv.org/abs/2110.04830) | arxiv 2110 | |



## 3. Inverse CAD Modeling

Here we focus on learning-based vector graphics generation **without** depending on vector training data, and traditional vectorization algorithms.


- Learning with external black-box (non-differentiable) rendering simulator

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Synthesizing Programs for Images using Reinforced Adversarial Learning](http://proceedings.mlr.press/v80/ganin18a/ganin18a.pdf) | ICML 2018 | [[Code]](https://github.com/deepmind/spiral) |
| [Unsupervised Doodling and Painting with Improved SPIRAL](https://arxiv.org/abs/1910.01007) | arxiv 1910 | [[Project]](https://learning-to-paint.github.io/) |

- Learning with built-in differentiable rendering module

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Towards Layer-wise Image Vectorization](https://ma-xu.github.io/LIVE/index_files/CVPR22_LIVE_main.pdf) | CVPR 2022 | [[code]](https://github.com/ma-xu/LIVE) [[project]](https://ma-xu.github.io/LIVE/) |
| [Paint Transformer: Feed Forward Neural Painting with Stroke Prediction](https://arxiv.org/abs/2108.03798) | ICCV 2021 | [[code]](https://github.com/Huage001/PaintTransformer) |
| [Rethinking Style Transfer: From Pixels to Parameterized Brushstrokes](https://arxiv.org/abs/2103.17185) | CVPR 2021 | [[code]](https://github.com/CompVis/brushstroke-parameterized-style-transfer) |
| [Im2Vec: Synthesizing Vector Graphics without Vector Supervision](https://arxiv.org/abs/2102.02798) | CVPR 2021 | [[Project]](http://geometry.cs.ucl.ac.uk/projects/2021/im2vec/) [[code]](https://github.com/preddy5/Im2Vec) |
| [Stylized Neural Painting](https://arxiv.org/abs/2011.08114) | CVPR 2021 | [[Code]](https://github.com/jiupinjia/stylized-neural-painting) [[project]](https://jiupinjia.github.io/neuralpainter/) |
| [Learning to Paint With Model-based Deep Reinforcement Learning](http://openaccess.thecvf.com/content_ICCV_2019/papers/Huang_Learning_to_Paint_With_Model-Based_Deep_Reinforcement_Learning_ICCV_2019_paper.pdf) | ICCV 2019 | [[code]](https://github.com/megvii-research/ICCV2019-LearningToPaint) |
| [Strokenet: A neural painting environment](https://openreview.net/forum?id=HJxwDiActX) | ICLR 2019 | [[Code]](https://github.com/vexilligera/strokenet) |
| [Neural Painters: A learned differentiable constraint for generating brushstroke paintings](https://arxiv.org/abs/1904.08410) | arxiv 1904 | [[Code]](https://github.com/reiinakano/neural-painters-pytorch) |
| [Learning to Sketch with Deep Q Networks and Demonstrated Strokes](https://arxiv.org/abs/1810.05977) | arxiv 1810 |  |
| [Unsupervised Image to Sequence Translation with Canvas-Drawer Networks](https://arxiv.org/abs/1809.08340) | arxiv 1809 |  |


- Vectorization

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Depixelizing pixel art](https://dl.acm.org/doi/abs/10.1145/1964921.1964994) | SIGGRAPH 2011 |  |
| [Perception-Driven Semi-Structured Boundary Vectorization](http://www.cs.ubc.ca/labs/imager/tr/2018/PerceptionDrivenVectorization/perception-driven-vectorization.pdf) | SIGGRAPH 2018 | [[Webpage]](http://www.cs.ubc.ca/labs/imager/tr/2018/PerceptionDrivenVectorization/) |
| [PolyFit: Perception-aligned Vectorization of Raster Clip-art via Intermediate Polygonal Fitting](http://www.cs.ubc.ca/labs/imager/tr/2020/ClipArtVectorization/paper.pdf) | SIGGRAPH 2020 | [[Webpage]](http://www.cs.ubc.ca/labs/imager/tr/2020/ClipArtVectorization/) [[Code]](https://github.com/dedoardo/polyfit) |
| [ClipGen: A Deep Generative Model for Clipart Vectorization and Synthesis](https://ieeexplore.ieee.org/abstract/document/9444657) | TVCG 2021 |  |
| [TCB-Spline-Based Image Vectorization](https://dl.acm.org/doi/10.1145/3513132) | TOG 2022 |  |
