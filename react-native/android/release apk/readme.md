#### prerequisite
yarn must be pre-installed with npm install -g yarn.
environment setup for react native.
path/to/jdk/bin and path/to/sdk/platform-tools should also be added to environment variables to use keytools service.

#### generate keystore file in project root
```
keytool -genkey -v -keystore release.keystore -alias releaseAlias -keyalg RSA -keysize 2048 -validity 10000
```

#### move file to ./android/app


#### update android/app/build.gradle
```
android {
....
  signingConfigs {
    release {
           storeFile file('release.keystore')
           storePassword 'releasePass'
           keyAlias 'releaseAlias'
           keyPassword 'releasePass' 
    }
  }
  buildTypes {
    release {
      ....
      signingConfig signingConfigs.release
    }
  }
}
```


#### must be an empty assets folder at :  android/app/src/main
#### must be an empty assets folder at :  android/app/src/main/res/

#### Add following to package.json's scripts section | this command declares settings
```
"release": "SET NODE_OPTIONS=--openssl-legacy-provider && npx react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res/assets"
```

#### move to android folder
```
cd android
```

#### release apk
```
./gradlew assembleRelease
```

#### Cli Automation
```
echo y | keytool -genkey -keystore ./android.jks -dname "n=Mark Jones, ou=JavaSoft, o=Sun, c=US" -alias android -keypass android  -storepass android -keyalg RSA -keysize 2048 -validity 2000
```




