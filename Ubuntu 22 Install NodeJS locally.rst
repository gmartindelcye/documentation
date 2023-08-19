Ubuntu 22 Install NodeJS locally
===============================

1. Install nvm:
   
   .. code-block:: bash
   
      curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash


2. Activate the changes to the current shell:

   .. code-block:: bash
   
      source ~/.profile


3. Install NodeJS:
   
   .. code-block:: bash
   
      nvm install node


Other commands
--------------

* List all available NodeJS versions:
   
   .. code-block:: bash
   
      nvm ls-remote


* List all installed NodeJS versions:   
  
    .. code-block:: bash

       nvm ls

* Switch to a specific NodeJS version:
  
    .. code-block:: bash
       
         nvm use <version>


* Run a Node script with a specific NodeJS version:

    .. code-block:: bash    

       nvm run <version> <script>   

    
         nvm ls