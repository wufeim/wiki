CCVL HuggingFace Group
**********************

HuggingFace group for private sharing of models and datasets within CCVL. Email `Wufei Ma <mailto:wufeim@gmail.com>`_ or `Yaoyao Liu <mailto:yliu538@jhu.edu>`_ to join the group.

* Group link: `huggingface.co <https://huggingface.co/ccvl>`_

Besides accessing data with Web UI, here are instructions of how to upload and download from terminal.

Logging In
----------

.. code::

    # You already have it if you installed transformers or datasets
    pip install huggingface_hub

    huggingface-cli login

Reference: `huggingface.co <https://huggingface.co/welcome>`_.

Uploading Data
--------------

Depending on the repo type, set :code:`repo_type` to :code:`dataset`, :code:`model`, or :code:`space`.

.. code::

    from huggingface_hub import HfApi
    api = HfApi()
    api.upload_file(
        path_or_fileobj='xxx.zip',
        path_in_repo='xxx.zip',
        repo_id='ccvl/repo_name',
        repo_type='dataset')

Reference: `huggingface.co <https://huggingface.co/docs/huggingface_hub/guides/upload#upload-a-file>`_.

Downloading a File
------------------

Depending on the repo type, set :code:`repo_type` to :code:`dataset`, :code:`model`, or :code:`space`.

.. code::

    from huggingface_hub import hf_hub_download
    hf_hub_download(
        repo_id='ccvl/repo_name',
        repo_type='dataset',
        filename='xxx.zip',
        local_dir='/path/to/xxx.zip',
        local_dir_use_symlinks=False)

Reference: `huggingface.co <https://huggingface.co/docs/huggingface_hub/guides/download#download-a-single-file>`_.
