
#### To setup react native correctly you need 4 things
1. OpenJdk
2. Android Sdk
3. Android Sdk build tools
4. Platform-tools

### 1. OpenJdk

#### update references
```
sudo apt update
```

#### install open jdk 11 (used by latest Android Studio (Bumblebee)
```
sudo apt install openjdk-11-jdk

```

#### check version
```
java -v
```

### 2. Android Sdk

#### install sdk wrapper apt
```
sudo apt install android-sdk
```

#### move to android-sdk directory
```
cd /usr/lib/android-sdk
```

#### install latest command line tools (zip file)
```
wget https://dl.google.com/android/repository/commandlinetools-linux-6609375_latest.zip
```


#### unzip tools 
```
unzip commandlinetools-linux-6609375_latest.zip -d cmdline-tools/latest
```

#### export latest bin path
```
export PATH=$ANDROID_HOME/cmdline-tools/latest/bin:$PATH
```

### Set Environment variables
#### goto root
```
cd ~
```

#### open bashrc to edit in cli
```
nano ~/.bashrc
```

#### scroll down to end of file using pagedown button or downkey. in end paste this:
```
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
export ANDROID_HOME=/usr/lib/android-sdk
export PATH=$PATH:$ANDROID_HOME/cmdline-tools/latest/tools/bin
```


### 3. install latest build tools

#### run sdkmanager to check it is install and configured.it should give you list of commands and flags you can use
```
sdkmanager
```


#### update sdkmanager to latest version
```
sdkmanager --update
```




