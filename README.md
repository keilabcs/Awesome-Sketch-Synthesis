# Awesome-Sketch-Synthesis

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

A collection of papers about Sketch Synthesis (Generation). Mainly focus on stroke-level vector sketch synthesis.

> Feel free to create a PR or an issue.

![examples](https://magenta.tensorflow.org/assets/sketch_rnn_demo/img/sketch_garden.gif)

**Outlines**

- [1. Datasets](#1-datasets)
- [2. Sketch-Synthesis Approaches](#2-sketch-synthesis-approaches)
  - [1) Category-to-sketch](#1-category-to-sketch)
  - [2) Photo-to-sketch](#2-photo-to-sketch)
  - [3) Text/Attribute-to-sketch](#3-textattribute-to-sketch)
  - [4) 3D shape-to-sketch](#4-3d-shape-to-sketch)
  - [5) Sketch(pixelwise)-to-sketch(vector)](#5-sketchpixelwise-to-sketchvector)
  - [6) Art-to-sketch](#6-art-to-sketch)


---

## 1. Datasets
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
    <td rowspan="6"><strong>Instance-level</strong></td>
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
    <td rowspan="4"><strong>Scene-level</strong></td>
    <td> <a href="http://www.cs.cmu.edu/~mengtial/proj/sketch/">Photo-Sketching</a> </td> 
    <td> WACV 2019 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :heavy_check_mark: </td> 
    <td> ScenePhoto-sketch paired </td>
  </tr>
  <tr>
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
  
</table>



## 2. Sketch-Synthesis Approaches

### 1) Category-to-sketch


<table>
  <tr>
    <td><strong>Level</strong></td>
    <td><strong>Paper</strong></td>
    <td><strong>Source</strong></td>
    <td><strong>Code/Project Link</strong></td>
  </tr>
  <tr>
    <td rowspan="4"><strong>Instance-level</strong></td>
    <td> <a href="https://openreview.net/pdf?id=Hy6GHpkCW">A Neural Representation of Sketch Drawings (sketch-rnn)</a> </td> 
    <td> ICLR 2018 </td> 
    <td> 
      <a href="https://github.com/tensorflow/magenta/tree/master/magenta/models/sketch_rnn">[Code]</a> 
      <a href="https://magenta.tensorflow.org/sketch-rnn-demo">[Project]</a> 
      <a href="https://magenta.tensorflow.org/assets/sketch_rnn_demo/index.html">[Demo]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/pdf/1709.04121.pdf">Sketch-pix2seq: a Model to Generate Sketches of Multiple Categories</a> </td> 
    <td>  </td> 
    <td> 
      <a href="https://github.com/MarkMoHR/sketch-pix2seq">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://idvxlab.com/papers/2019AAAI_Sketcher_Cao.pdf">AI-Sketcher : A Deep Generative Model for Producing High-Quality Sketches</a> </td> 
    <td> AAAI 2019 </td> 
    <td> <a href="https://facex.idvxlab.com/">[Project]</a> </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/pdf/1901.03427.pdf">Stroke-based sketched symbol reconstruction and segmentation (stroke-rnn)</a> </td> 
    <td> </td> 
    <td> </td>
  </tr>
  
</table>

---

### 2) Photo-to-sketch

- vector image generation

<table>
  <tr>
    <td><strong>Level</strong></td>
    <td><strong>Paper</strong></td>
    <td><strong>Source</strong></td>
    <td><strong>Code/Project Link</strong></td>
  </tr>
  <tr>
    <td rowspan="1"><strong>Facial</strong></td>
    <td> <a href="https://dl.acm.org/citation.cfm?id=2461964">Style and abstraction in portrait sketching</a> </td> 
    <td> TOG 2013 </td> 
    <td>
    </td>
  </tr>
  <tr>
    <td rowspan="3"><strong>Instance-level</strong></td>
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
    <td rowspan="1"><strong>Scene-level</strong></td>
    <td> <a href="https://arxiv.org/pdf/1901.00542.pdf">Photo-Sketching: Inferring Contour Drawings from Images</a> </td> 
    <td> WACV 2019 </td> 
    <td>
      <a href="https://github.com/mtli/PhotoSketch">[Code]</a> 
      <a href="http://www.cs.cmu.edu/~mengtial/proj/sketch/">[Project]</a> 
    </td>
  </tr>
</table>

---

### 3) Text/Attribute-to-sketch

| Level | Paper | Source | Code/Project Link |
| --- | --- | --- | --- |
| **Scene-level** | [Scones: Towards Conversational Authoring of Sketches](http://people.eecs.berkeley.edu/~eschoop/docs/scones.pdf) | IUI 2020 |  |
| **Scene-level** | [Sketchforme: Composing Sketched Scenes from Text Descriptions for Interactive Applications](https://arxiv.org/pdf/1904.04399.pdf) | UIST 2019 |  |
| **Facial** | [Text2Sketch: Learning Face Sketch from Facial Attribute Text](https://ieeexplore.ieee.org/abstract/document/8451236) | ICIP 2018 |  |

---

### 4) 3D shape-to-sketch

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [DeepShapeSketch : Generating hand drawing sketches from 3D objects](https://shizhezhou.github.io/projects/DeepFreeHandSke2019/deepFreehandSke2019.pdf) | IJCNN 2019 |  |
| [Neural Contours: Learning to Draw Lines from 3D Shapes](https://people.cs.umass.edu/~dliu/papers/NeuralContours.pdf) | CVPR 2020 | [[project]](https://people.cs.umass.edu/~dliu/projects/NeuralContours/) [[code]](https://github.com/DifanLiu/NeuralContours) |

---


### 5) Sketch(pixelwise)-to-sketch(vector)


This means translating a pixelwise sketch into a sequential sketch imitating human's drawing order. The appearance of the sequential sketch is exactly the **same** as the pixelwise one.


| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Animated Construction of Line Drawings](http://sweb.cityu.edu.hk/hongbofu/projects/animatedConstructionOfLineDrawings_SiggA11/animatedConstructionOfLineDrawings_SiggA11.pdf) | SIGGRAPH ASIA 2011 | [[Project]](http://sweb.cityu.edu.hk/hongbofu/projects/animatedConstructionOfLineDrawings_SiggA11/) [[code]](http://sweb.cityu.edu.hk/hongbofu/projects/animatedConstructionOfLineDrawings_SiggA11/Viewer_src.zip) [[Demo]](http://sweb.cityu.edu.hk/hongbofu/projects/animatedConstructionOfLineDrawings_SiggA11/Viewer.zip) |

---

### 6) Art-to-sketch

Here we list sketch synthesis based on other image types, like Manga and line art.

- Hand drawn line art (a.k.a. Sketch Simplification)


| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Closure-aware Sketch Simplification](http://www.cse.cuhk.edu.hk/~ttwong/papers/sketch/sketch.pdf) | SIGGRAPH ASIA 2015 | [[Project]](https://www.cse.cuhk.edu.hk/~ttwong/papers/sketch/sketch.html) |
| [Learning to Simplify: Fully Convolutional Networks for Rough Sketch Cleanup](https://esslab.jp/publications/SimoSerraSIGGRAPH2016.pdf) | SIGGRAPH 2016 | [[Code]](https://github.com/bobbens/sketch_simplification) [[Project]](https://esslab.jp/~ess/en/research/sketch/) |
| [Mastering Sketching: Adversarial Augmentation for Structured Prediction](https://esslab.jp/~ess/publications/SimoSerraTOG2018.pdf) | SIGGRAPH 2018 | [[Code]](https://github.com/bobbens/sketch_simplification)  [[Project]](https://esslab.jp/~ess/en/research/sketch_master/) |
| [Real-Time Data-Driven Interactive Rough Sketch Inking](https://esslab.jp/~ess/publications/SimoSerraSIGGRAPH2018.pdf) | SIGGRAPH 2018 | [[Code]](https://github.com/bobbens/line_thinning) [[Project]](https://esslab.jp/~ess/en/research/inking/) |
| [StrokeAggregator: Consolidating Raw Sketches into Artist-Intended Curve Drawings](https://www.cs.ubc.ca/labs/imager/tr/2018/StrokeAggregator/StrokeAggregator_authorversion.pdf) | SIGGRAPH 2018 | [[Project]](https://www.cs.ubc.ca/labs/imager/tr/2018/StrokeAggregator/) |
| [Perceptual-aware Sketch Simplification Based on Integrated VGG Layers](https://ieeexplore.ieee.org/abstract/document/8771128/) | TVCG 2019 |  |

- Manga (Comics)

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Deep extraction of manga structural lines](https://dl.acm.org/citation.cfm?id=3073675) | SIGGRAPH 2017 | [[Code]](https://github.com/ljsabc/MangaLineExtraction) |
