Ubuntu 22 WSL Intellij Idea Installation
========================================

In WINDOWS
----------

1. Power Shell Admin:

    .. code-block::

        choco install VcXsrv


    This install the x-server in windows


2. Create Desktop shortcut, in the properties::

    "C:\Program Files\VcXsrv\vcxsrv.exe" :0 -ac -terminate -lesspointer -multiwindow  -clipboard -wgl -dpi auto


3. Name it **VcXsrv** and run it.

4. Locate your windows ip:

    .. code-block::

        ipconfig


In WSL
------

1. Create an environment variable to point to windows machine.

    .. code-block:: bash

        $ export DISPLAY=<windows IP>:0


    You have to change this every time the IP changes.


2. Update system

    .. code-block:: bash

        $ sudo apt update
        $ sudo apt upgrade -y


3. Install x-server utilities to check that the configuration is working.

    .. code-block:: bash

        $ sudo apt install x11-apps


4. run xeyes app to check.

    .. code-block:: bash

        $ xeyes


4. Install JRE.

    .. code-block:: bash

        $ sudo apt install default-jre


5. Download Intellij Idea.

    a. with `wget` or `curl`

    .. code-block:: bash

        $ wget https://download.jetbrains.com/idea/ideaIU-xxxx.x.x.tar.gz


    b. Through windows download file, and use the next command to copy to wsl

    .. code-block:: bash

        $ cp /mnt/c/Users/<user>/Downloads/ideaIU-xxxx.x.x.tar.gz .


6. Uncompress file

    .. code-block:: bash

        $ tar zxf ideaIU-xxxx.x.x.tar.gz


7. Change to directory and run

    .. code-block:: bash

        $ cd idea-UI-<version>/bin
        $ ./idea.sh

