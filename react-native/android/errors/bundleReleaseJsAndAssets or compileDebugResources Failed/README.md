####  1. delete android/app/src/main/assets or android/app/src/main/res/assets 
####  2. create empty assets folder in main
####  3. open terminal in project root & run following commands
```
react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res
```

```
cd android
```


```
gradlew clean
```


```
gradlew assembleRelease -x bundleReleaseJsAndAssets
```
