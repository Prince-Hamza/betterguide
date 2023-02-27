#### prerequisite
environment setup for react native.
path/to/jdk/bin and path/to/sdk/platform-tools should also be added to environment variables to use keytools service.

#### generate keystore file in project root
```
keytool -genkey -v -keystore your_key_name.keystore -alias your_key_alias -keyalg RSA -keysize 2048 -validity 10000
```

#### move file to ./android/app


#### update android/app/build.gradle
```
android {
....
  signingConfigs {
    release {
      storeFile file('your_key_name.keystore')
      storePassword 'your_key_store_password'
      keyAlias 'your_key_alias'
      keyPassword 'your_key_file_alias_password'
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


#### delete existing assets folder (if any) at :  android/app/src/main/res/

#### create an empty assets folder at :  android/app/src/main/res/

#### declare settings
```
npx react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/assets/index.android.bundle 
--assets-dest android/app/src/main/res/
```

#### move to android folder
```
cd android
```

#### release apk
```
./gradlew assembleRelease
```






