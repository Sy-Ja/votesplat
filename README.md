# VoteSplat

This is the repository that contains source code for the [VoteSplat](http://arxiv.org/abs/2506.22799)

## Abstract
3D Gaussian Splatting (3DGS) has become horsepower in high-quality, real-time rendering for novel view synthesis of 3D scenes. However, existing methods focus primarily on geometric and appearance modeling, lacking deeper scene understanding while also incurring high training costs that complicate the originally streamlined differentiable rendering pipeline. To this end, we propose VoteSplat, a novel 3D scene understanding framework that integrates Hough voting with 3DGS. Specifically, Segment Anything Model (SAM) is utilized for instance segmentation, extracting objects, and generating 2D vote maps. We then embed spatial offset vectors into Gaussian primitives. These offsets construct 3D spatial votes by associating them with 2D image votes, while depth distortion constraints refine localization along the depth axis. For open-vocabulary object localization, VoteSplat maps 2D image semantics to 3D point clouds via voting points, reducing training costs associated with high-dimensional CLIP features while preserving semantic unambiguity. Extensive experiments demonstrate VoteSplat’s effectiveness in open-vocabulary 3D instance localization, 3D point cloud understanding, click-based 3D object localization, hierarchical segmentation, and ablation studies.

## Pipeline
<img width="944" alt="votesplat_pipeline" src="https://github.com/user-attachments/assets/2c39e223-ae04-4423-ab6d-6599d96ab0d9" />

Three main steps in VoteSplat pipeline:  
(a) We first deploy SAM to automatically generate segmentation masks for all instances independently across different views.  
(b) For each segmented mask, we compute the instance center to construct the 2D Vote Map.  
(c) By projecting 3D votes into pixel space through splatting and computing the voting loss together with the previous 2D voting map, each Gaussian primitive forming an instance is ensured to learn an offset vector pointing toward the instance center. For simplicity, we omit the rendering process and density control of other Gaussian parameters.  



## BibTeX
If you find VoteSplat useful for your work please cite:
```

```

