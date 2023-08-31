Accessing CCVL Clusters
***********************

To access CCVL clusters, you need to connect to (i) JHU VPN, or (ii) CCVL jump machine. JHU VPN is highly recommended for faster and more stable connections.

Connecting to JHU VPN
---------------------

**You need an active JHU accout and ID to access JHU VPN.**

Instructions of how to apply for access and connect to JHU VPN is available `here <https://support.cs.jhu.edu/wiki/VPN_-_JHU>`_.

Connecting to CCVL Jump Machine
-------------------------------

Add the following to your :code:`~/.ssh/config`:

.. code::

    Host ccvl_jm
        HostName 139.zzs.one
        User ccvl

The password is :code:`o9MF!!*vrT1OYpYQ`.

Connecting to CCVL Machines
---------------------------

We use :code:`ccvl11` as an example. Add the following to your :code:`~/.ssh/config`:

.. code::

    Host ccvl11
        HostName ccvl11.ccvl.jhu.edu
        User username
        ProxyCommand ssh ccvl_jm -W %h:%p

.. note::

    The CCVL jump machine may not recognize domain names such as :code:`ccvl11.ccvl.jhu.edu`. You may need to change :code:`ccvl11.ccvl.jhu.edu` to the exact IP address. Ask lab members for more information.

Then connect to the server with your password:

.. code::

    ssh ccvl11

If you are connecting with CCVL jump machine, you will be prompted twice with the first time entering the password to :code:`ccvl_jm` and the second time to :code:`ccvl11`.

SSH Key Authentication
----------------------

We recommend connecting to CCVL servers with SSH key authentication.

1. First generate SSH key with :code:`ssh-keygen`. Use default file location and empty passphrase.
2. Copy the key to servers with :code:`ssh-copy-id -i ~/.ssh/id_rsa ccvl_jm` and :code:`ssh-copy-id -i ~/.ssh/id_rsa ccvl11`.
3. Add :code:`IdentityFile ~/.ssh/id_rsa` to both the :code:`ccvl_jm` config and the :code:`ccvl11` config.
