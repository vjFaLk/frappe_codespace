# Setup

It's ridiculously easy - 

![open-with-codespaces](https://docs.github.com/assets/cb-138303/images/help/codespaces/new-codespace-button.png)

Setup happens in two steps - 
1. Github will first create a codespace
2. Once the codespace is initialized (you will see VSCode UI) a script runs that will -
   1. Create a bench with Frappe develop branch and configure it
   2. Create a new site called dev.localhost with the password `admin`
   3. Enables developer mode, sets dev.localhost as default site 

# Features

1. A fresh bench is initialized with the latest Frappe develop code along with a new site when the codespace is initially created
1. Pre-configured `launch.json` with the following options -
   1. Web Server
   2. 3 Workers
   3. Bench Watch
2. Pre-installed Extensions
3. Pre-configured [SQLTools](https://marketplace.visualstudio.com/items?itemName=mtxr.sqltools)

# Notes 

- The init script takes some time, so you can track the progress by selecting the "Codespaces : View Creation Log" from the command palette. Ideally you should wait until this process is completed. 
- The Procfile generated includes `bench serve` so `bench start` will work as usual, however if you'd like to use the debugger, you want to remove the `bench serve` line in the Procfile and run `Bench Web` from VSCode instead
- I've configured the settings so that the Python extension points to the correct python in the venv be default, however if you're having issues with VSCode's linter behaving badly or the launch options not working (frappe not found) do check which python binary VSCode is using
- Github Codespaces works with the native version of VSCode for virtually native experience, you only need to install the Codespaces extension and configure it to connect to your Codespace. I recommend doing this over using the browser. 