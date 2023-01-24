
### Compatibility for React Native 0.66.4

#### build.gradle
```
// Top-level build file where you can add configuration options common to all sub-projects/modules.

buildscript {
    ext.kotlin_version = '1.4.0'
    ext {
      buildToolsVersion = '30.0.2'
        minSdkVersion = 21
        compileSdkVersion = 31
        targetSdkVersion = 31
        ndkVersion = "20.1.5948944"

        supportLibVersion   = "29.0.3"
        androidMapsUtilsVersion = "2.2.2"

        googlePlayServicesVersion = "17.0.0"
          ndkVersion = "21.4.7075529" // may bi remove
          kotlin_version = "1.5.0"
    }
    repositories {
        mavenCentral()
        google()
        jcenter()
    }
    dependencies {
        classpath("com.android.tools.build:gradle:4.1.0")
        classpath 'com.google.gms:google-services:4.3.3'
        classpath "org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlin_version"
        // NOTE: Do not place your application dependencies here; they belong
        // in the individual module build.gradle files
    }
}

def REACT_NATIVE_VERSION = new File(['node', '--print',"JSON.parse(require('fs').readFileSync(require.resolve('react-native/package.json'), 'utf-8')).version"].execute(null, rootDir).text.trim())


allprojects {

       configurations.all {
    resolutionStrategy {
        // Remove this override in 0.65+, as a proper fix is included in react-native itself.
        force "com.facebook.react:react-native:" + REACT_NATIVE_VERSION
    }
    }
    
    repositories {
        mavenLocal()
        maven {
            // All of React Native (JS, Obj-C sources, Android binaries) is installed from npm
            url("$rootDir/../node_modules/react-native/android")
        }
           
        maven {

            // Android JSC is installed from npm
            url("$rootDir/../node_modules/jsc-android/dist")
        }
        // ADD THIS
        maven { url 'https://maven.google.com' }

      // ADD THIS
        maven { url "https://www.jitpack.io" }

          maven {
            url "https://android-sdk.is.com"
             }
        google()
        jcenter()
    }
}

```


#### navigation packages

```
    "@react-navigation/drawer": "5.2.0",
    "@react-navigation/native": "^5.9.2",
    "@react-navigation/stack": "^5.14.1",
```

