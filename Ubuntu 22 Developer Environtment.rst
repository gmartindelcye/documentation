Ubuntu 22.04 Development Environment
==========================================

The 22.04 version of Ubuntu lacks certain libraries that older versions install by defaukt.
So in order to get the right developer environment have to be installed.

(This have ben tested with Ubuntu 22.04, Ubuntu Mate 22.04 and Ubuntu 22.04 WSL.)

Steps
-----

1. Update and upgrade your distribution:

.. code-block:: shell

    sudo apt update && sudo apt upgrade -y


2. Install required packages:

.. code-block:: shell

    sudo apt install -y git python3-venv build-essential -y


3. Install missing packages:

.. code-block:: shell

    sudo apt install -y curl python3-pip libbz2-dev lzma liblzma-dev libsqlite3-dev libreadline-dev libncurses-dev libffi-dev libssl-dev openssl python3-tk tk-dev


    (The two last ones are not needed for Ubuntu WSL: python3-tk and tk-dev)


4. Install pyenv 

.. code-block:: shell

    curl https://pyenv.run | bash


5. Copy the pyenv configuration commands to .bashrc and .profile

.. code-block:: shell

    echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
    echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
    echo 'eval "$(pyenv init -)"' >> ~/.bashrc

    echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.profile
    echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.profile
    echo 'eval "$(pyenv init -)"' >> ~/.profile


6. Reinitialize the shell in order to the later configuration take action.

.. code-block:: shell

    eval $SHELL


7. You can verify that pyenv is working. The result of the following command will show you that python is installed in its default ubuntu version.

.. code-block:: shell

    pyenv versions


8. If you whish to install a diferent python version, say 3.9.15 then:

.. code-block:: shell

    pyenv install 3.9.15



You can verify the installation

.. code-block:: shell

    pyenv versions


9. Set the version of python to your environment, either localy ``local`` for this session, or permanently ``global``. For this case we wil use permanently.

.. code-block:: shell

    pyenv global 3.9.15


10. Install pdm.

.. code-block:: shell

    curl -sSL https://raw.githubusercontent.com/pdm-project/pdm/main/install-pdm.py | python3 -

11. Add to .bashrc:
    
.. code-block:: shell

    export PATH="/home/$USER/.local/bin:$PATH"