DST Dataset
***********

DST-1k for Image Classification
-------------------------------

Under development. Available upon request.

DST-Pose for Pose Estimation
----------------------------

Following the same data generation process, we create DST-Pose for pose estimation, with same categories as PASCAL3D+ (10) and ObjectNet3D (10). Common experiment settings include:

1. **Zero-shot pose estimation:** Pretrain pose estimation model on DST-Pose and directly test the zero-shot performance on PASCAL3D+ or Object3D test set.
2. **Pose estimation with unsupervised domain adaptation:** Pretrain pose estimation model on DST-pose first, then adapt the model to real images with some UDA approach before evaluation.
3. **Pose estimation with synthetic pretraining datasets:** Pretrain pose estimation model on DST-Pose first, then finetune the model on the training set of PASCAL3D+ or ObjectNet3D before evaluation.

The raw data is available here: `huggingface.co <https://huggingface.co/datasets/ccvl/DST-pose>`_ (requires `CCVL group access <https://wufei-wiki.readthedocs.io/en/latest/ccvl_huggingface.html>`_). *The preprocessing code will be available soon.*

**References:**

1. `Adding 3D geometry control to diffusion models <https://arxiv.org/abs/2306.08103>`_ by Wufei Ma, Qiaho Liu, and Jiahao Wang et al.
2. `Robust category-level 3D pose estimation from synthetic data <https://arxiv.org/abs/2305.16124>`_ by Jiahao Yang et al.
