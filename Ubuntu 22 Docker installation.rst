Ubuntu 22.04 Docker Installation
================================

1. Update Ubuntu software packages:

    .. code-block:: bash

        sudo apt-get update
    ```

2. Install neccessary packages:

    .. code-block:: bash

        sudo apt-get install apt-transport-https ca-certificates curl gnupg lsb-release  software-properties-common -y


3. Add Docker GPG key:

    .. code-block:: bash

        curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg


4. Add Docker repository:

    .. code-block:: bash

        echo \
        "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
        $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

    
5. Update Ubuntu software packages:

    .. code-block:: bash

        sudo apt-get update


6. Establish docker version:

    .. code-block:: bash

        apt-cache policy docker-ce


7. Install Docker:

    .. code-block:: bash

        sudo apt-get install docker-ce docker-ce-cli docker-compose-plugin containerd.io -y


8. Verify Docker installation:

    .. code-block:: bash

        sudo systemctl status docker


    Press ``q`` to exit the status screen.


9. Enable Docker to start on boot:

    .. code-block:: bash

        sudo systemctl enable docker


10. Add user to docker group:

    .. code-block:: bash

        sudo usermod -aG docker $USER


11. Re-log to apply the group changes.:

    .. code-block:: bash

        exec su -l $USER


11. Verify Docker version:

    .. code-block:: bash

        docker --version


12. Test Docker installation:

    .. code-block:: bash

        docker run hello-world


13. Check docker-compose version:

    .. code-block:: bash

        docker compose version