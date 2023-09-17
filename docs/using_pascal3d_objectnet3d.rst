Preprocessing PASCAL3D+ and ObjectNet3D
***************************************

.. warning::

   **DO NOT DISTRIBUTE.** This wiki page is for internal use only. It is forbidden to copy, forward, or in any way reveal the contents of this wiki to anyone.

For 3D or 6D pose estimation, we preprocess the images in PASCAL3D+ and ObjectNet3D:

1. (Optional) Resize images so all objects in the final data are roughly the same scale.
2. Crop or pad the images so they have the same image sizes.
3. (Optional) For NeMo projects, compute keypoint locations given the pose annotations and a known CAD model.

The propcessing code can be found in the `NeMo repo <https://github.com/wufeim/NeMo>`_ at :code:`data/prepare_pascal3d.py` and :code:`data/prepare_objectnet3d.py`.

Preparing PASCAL3D+ and Occluded PASCAL3D+
------------------------------------------

.. code::

    python3 prepare_pascal3d.py \
        --config config/datasets/pascal3d.yaml


**Options in YAML config:**

* :code:`pad_texture`: If :code:`True`, use describable textures when padding.
* :code:`occ_levels`: The occlusion levels we prepare for training and validation data.
* :code:`single_mesh`: Type of mesh we generate.
* :code:`root_path`: Path to the generated data.
* :code:`training_only`: If :code:`True`, skip validation data.
* :code:`image_sizes`: Image sizes of the output images.
* :code:`mesh_path`: Path to the meshes used for generating 3D keypoint annotations.
* :code:`prepare_mode`: Preparation mode, :code:`first` or :code:`all`.
* :code:`augment_by_dist`: If :code:`True`, augment samples by object distances (scales); commonly used for 6D pose estimation training.


Preparing ObjectNet3D
---------------------

.. code::

    python3 prepare_objectnet3d.py \
        --config config/datasets/prepare_objectnet3d.yaml

**Options in YAML config:**

* :code:`pad_texture`: If :code:`True`, use describable textures when padding.
* :code:`single_mesh`: Type of mesh we generate.
* :code:`root_path`: Path to the generated data.
* :code:`training_only`: If :code:`True`, skip validation data.
* :code:`image_sizes`: Image sizes of the output images.
* :code:`mesh_path`: Path to the meshes used for generating 3D keypoint annotations.
* :code:`prepare_mode`: Preparation mode, :code:`first` or :code:`all`.
* :code:`augment_by_dist`: If :code:`True`, augment samples by object distances (scales); commonly used for 6D pose estimation training.
