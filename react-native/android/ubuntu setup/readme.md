
#### To setup react native correctly you need 4 things
1. OpenJdk
2. Android Sdk
3. Set environment variables
4. Android Sdk build tools
5. Platform-tools

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

#### create cmdline directory (if does not exist)

```
sudo mkdir cmdline-tools
```

#### install latest command line tools (zip file)
```
wget https://dl.google.com/android/repository/commandlinetools-linux-6609375_latest.zip
```

#### unzip tools 
```
unzip commandlinetools-linux-6609375_latest.zip -d cmdline-tools
```
it will create a another cmdline-tools folder in cmdline-tools

#### rename unzipped folder
```
cd cmdline-tools
```
```
sudo mv cmdline-tools tools
```

#### Check: your directory structure should now be : /usr/lib/android-sdk/cmdline-tools/tools. in tools you would have files relevant to sdk.
```
cd /usr/lib/android-sdk/cmdline-tools/tools
```
```
ls
```







### 3. Set Environment variables

by default components in android-sdk are obsolete due to shortcomings of apt packager. we will update / install new components.

#### goto root (optional)
```
cd ~
```

#### open bashrc to edit in cli
```
nano ~/.bashrc
```

#### scroll down to end of file using pagedown button or downkey. in end paste this:
```
export ANDROID_SDK_ROOT=/usr/lib/android-sdk
export PATH=$PATH:$ANDROID_SDK_ROOT/cmdline-tools/tools/bin
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
```

#### globalize changes
```
source ~/.bashrc
```

#### Check environment variables.you should see var value
```
$JAVA_HOME
```
```
$ANDROID_SDK_ROOT
```






### 4. install latest build tools

#### Set administrator access to avoid filesystem issues
```
sudo chown $USER:$USER $ANDROID_SDK_ROOT -R
```

#### run sdkmanager to check it is install and configured.it should give you list of commands and flags you can use
```
sdkmanager
```


#### update sdkmanager to latest version
```
sdkmanager --update
```

#### latest platform tools
```
sdkmanager "build-tools;31.0.0"
```


#### Check : you must be able to see folder 31.0.0 in $ANDROID_SDK_ROOT/build-tools
```
cd $ANDROID_SDK_ROOT/build-tools
```
```
ls
```





