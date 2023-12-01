DST3D
*****

.. warning::

   **DO NOT DISTRIBUTE.** This wiki page is for internal use only. It is forbidden to copy, forward, or in any way reveal the contents of this wiki to anyone.

The DST3D code is now released `here <https://github.com/wufeim/DST3D>`_. Please refer to the documentation for installation and data generation instructions. The codebase reproduces the following results:

* Data generation with DST3D for various downstreamt tasks, including image classification on ImageNet-1k, 3D pose estimation on PASCAL3D+ and ObjectNet3D, and 3D object detection on Omni3D.
* Diverse prompt generation with LLM (LLaMA and MiniGPT-4).
* K-fold Consistency Filter (KCF) to remove images with possibly wrong 3D annotations.

For the complete experimental results, please refer to our paper on `arXiv <https://arxiv.org/abs/2306.08103>`_.

Citation
--------

If you find this repository helpful, please consider citing:

| @article{ma2023adding,
|   title={Adding 3D Geometry Control to Diffusion Models},
|   author={Ma, Wufei and Liu, Qihao and Wang, Jiahao and Wang, Angtian and Liu, Yaoyao and Kortylewski, Adam and Yuille, Alan},
|   journal={arXiv preprint arXiv:2306.08103},
|   year={2023}
| }
