_**runs-on: ubuntu-latest**_: 

This specifies the Runner that will run on a GitHub-hosted virtual machine with the latest version of Ubuntu.

_**uses: actions/checkout@v3**_: 

This is an action that checks out the code from your repository into the runner (the virtual machine). 
Without this step, the job wouldn’t have access to your project’s code, and the following steps wouldn’t be able to run tests or install dependencies.

_**uses: actions/setup-node@v3**_: 

This action sets up the Node.js environment on the runner. It installs Node.js, so you can run Node.js commands in subsequent steps.

_**cache: 'npm'**_: 

This configures the action to cache the npm dependencies (the node_modules folder) to speed up future workflows. 
It avoids re-installing the same dependencies every time, saving time.

_**run: npm install**_:

This runs the command npm install to install all the dependencies listed in your package.json file.
These are the dependencies required for your project to work (like libraries and frameworks). In our case the dependecies we need to need to install are found in dependencies and dev dependencies scripts, and they are:

        "bcryptjs": "^2.4.3",
        
        "cors": "^2.8.5",
        
        "express": "^4.19.2",
        
        "jsonwebtoken": "^9.0.2",
        
        "mongoose": "^8.5.3"
        
        "nodemon": "^3.1.4"
_
**run: npm test**_:

npm test is a command used to run the test suite for a Node.js application. It is part of the npm (Node Package Manager) ecosystem and is typically defined in a project’s package.json file.
When you run npm test, npm will look for a test script defined in the scripts section of package.json. By default, npm test runs the command specified under the test property of scripts. 
In our case the script under test is ""echo \"Error: no test specified\" && exit 1"". This means that when you run npm test, it will simply print an error message ("Error: no test specified") and 
then exit with a status of 1, which indicates failure.
