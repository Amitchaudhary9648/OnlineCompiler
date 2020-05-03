# OnlineCompiler
## What is it? ##
It is a *Docker* based compiler to run untrusted code and return the output to your app. Users can submit their code in any of the supported languages. The system will test the code in an isolated environment. This way you do not have to worry about untrusted code possibly damaging your server intentionally or unintentionally.
You can use this system to allow your users to compile their code right in the browser.
## How does it work? ##

The client-side app submits the code and the languageID to the server through the API. The API then creates a new *Docker* container and runs the code using the compiler/interpreter of that language. The program runs inside a virtual machine with limited resources and has a time-limit for execution (20s by default). Once the output is ready it is sent back to the client-side app. The *Docker* container is destroyed and all the files are deleted from the server.
## Installation Instructions ##

* Go to the 'Setup' directory.
    - Open the Terminal as root user
    
    - Execute the script **Install_*.sh**, select the file which best suites your Operating System description. This will install the Docker and NodeJs pre-requisites to your system and create an image called 'virtual_machine' inside the Docker. DockerVM may take around 20 to 30 minutes depending on your internet connection.
    
    - Once the Install script executes successfully, copy the folder named 'API' to your desired path.
    
    - Open app.js in the API folder and set the variable values as follows.
    
    	1. **timeout_value**: The time in seconds till which the API should wait for the output of the code before generating an "Execution Timed Out" message.
        2. **port**: The port on which the server will listen, the default port is 80.
        
    - To test the installation, open a new terminal windows, cd to the API folder and type the following command
	```
    $ npm install .
    ```
	to install all needed nodejs modules, followed by
	
    ```
    $ sudo nodejs app.js
    ```
    - If everything has been setup correctly in app.js file, you will see the following message on your terminal
    ```
    Listening at <port_number>
    ```

    - Navigate your browser to http://127.0.0.1/
    
    ## Supported Operating Systems ##
    The CompileBox API has been installed and run succesfully on the following platforms
	- Ubuntu 12.04 LTS
    - Ubuntu 13.10
    - Ubuntu 14.04 LTS
    - Ubuntu 16.04 LTS
    - Linux Mint 15 
    - CentOS 6 (root required not sudo)

