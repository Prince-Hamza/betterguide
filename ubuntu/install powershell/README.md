#### Update the list of packages
``` 
sudo apt-get update 
```


#### Install pre-requisite packages.
 ```
 sudo apt-get install -y wget apt-transport-https software-properties-common
 ```
 
#### Download the Microsoft repository GPG keys
````
wget -q https://packages.microsoft.com/config/ubuntu/$(lsb_release -rs)/packages-microsoft-prod.deb
```


