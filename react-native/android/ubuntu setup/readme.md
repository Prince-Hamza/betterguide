
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

#### set as Android Home environment variable
```
export ANDROID_HOME=/usr/lib/android-sdk
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







