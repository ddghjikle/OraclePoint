# OraclePoints: A Hybrid Neural Representation for Oracle Character Processing (ACM MM 2023)
Official implementation of ["**[OraclePoints: A Hybrid Neural Representation for Oracle Character Processing (ACM MM 2023)](https://doi.org/10.1145/3581783.3612534)**"], *[Runhua Jiang](https://scholar.google.com.hk/citations?hl=zh-CN&view_op=list_works&gmla=AOV7GLOtVSSA5YAZIfaFwu9aInPr2OI4l-brSoherrpowMD_NndZ-hEbqmPezX6qy8zAq-KrcP1em6MjegzbUfzLK7U&user=mD3lO60AAAAJ)*, *Yongge Liu*, *Boyuan Zhang*, *Xu Chen,* *Deng Li*, *[YaHong Han](http://cic.tju.edu.cn/faculty/hanyahong/index.html)*.
DOI: https://doi.org/10.1145/3581783.3612534

> **Abstract:** *Oracle Bone Inscriptions (OBI) are ancient hieroglyphs originated in China and are considered one of the most famous writing systems in the world. Up to now, thousands of OBIs have been discovered, which require deciphering by experts to understand their contents. Experts typically need to restore, classify, and compare each character with previous inscriptions. Although existing research can assist with one of these operations, their performance falls short of practical requirements. In this work, we propose the OraclePoints framework, which represents OBI images as hybrid neural representations comprising features of images and point sets. The image representation provides inscription appearance and character structure, while the point representation makes it easy and effective to distinguish characters and noises. In addition, we demonstrate that OraclePoints can be easily integrated with existing models in a plug-and-play manner. Comprehensive experimentations demonstrate that the proposed hybrid neural representation framework supports a range of OBI tasks, including character image retrieval, recognition, and denoising. It is also demonstrated that OraclePoints is helpful for deciphering OBI by linking ancient characters to modern Chinese characters.*

### The codes will be released once they are annotated.

## 1. Introduction

<p align="center">
    <img src='/introduction.png' width=700/>
</p>

**Top row:**

An illustration of our motivation. Both noises and characters within OBIs are presented by white pixels with different patterns. Therefore, distinguishing characters from various noises is essential to learn effective representations.

**Bottom row:**

By representing oracle image as a set of points, the hybrid representation enables robust retrieval and recognition of scanned character images that are affected by random noise, exhibit different styles (\emph{i.e.}, the right result in the top line) and contain large blank spaces (\emph{i.e.}, the left image in the second line). In addition, character structures in degraded images can be effectively restored by identifying discrete noises and restoring local structure for each point set. Notably, the hybrid representation also facilitates the matching of modern Chinese to ancient oracle characters.


## 2. Method

<p align="center">
    <img src='/architecture.png' width=800/>
</p>

Overview of the proposed OraclePoints. It utilizes five stages to extract point representations for the task-specific network.

<p align="center">
    <img src='/hybrid1.png' width=800/>
</p>

A context cluster block for learning neural representations of point sets. By the point embedding transformation, the input image is transformed to multiple point sets. Then, each of them is initialized with a center point. Features of these clustered points are aggregated to the center point, and then dispatched within a cluster to obtain point representations.

## 3. Usage
### 3.1 Data
The datasets used in the paper are available at the following links. Please download and place them according to instructions of each task.
* [Image-retrieval](https://github.com/ddghjikle/OraclePoint) (Preparing for releasing)
* [Oracle-241](https://github.com/wm-bupt/STSN)
* [Noisy-character-image-benchmark](https://github.com/daqians/Noisy-character-image-benchmark)
* [AncientChineseCharSim](https://github.com/YangChiJLU/AncientChineseCharSim)


### 3.2 Dependencies

* Python 3.6.15
* PyTorch 1.9.0
* numpy
* Pillow
* torchvision
* scipy

### 3.3 Train

**To Do.**

### Citation
If you find our code or paper useful, please consider citing:
```
@inproceedings{jiang2023oraclepoint,
  title={OraclePoints: A Hybrid Neural Representation for Oracle Character Processing},
  author={Runhua Jiang, Yongge Liu, Boyuan Zhang, Xu Chen, Deng Li, Yahong Han},
  booktitle={Proceedings of the 31st ACM International Conference on Multimedia},
  year={2023}
}
```

### Acknowledgments

The code is build on both [STSN](https://github.com/wm-bupt/STSN), [CharFormer](https://github.com/daqians/CharFormer), [AncientChineseCharSim](https://github.com/wm-bupt/STSN), [ACNet](https://github.com/leftthomas/ACNet), [EGFF](https://github.com/leftthomas/EGFF), and especially [Context-cluster](https://github.com/ma-xu/Context-Cluster). Thanks them very much for their sharing.
