
### Compatibility for React Native 0.66.4

#### build.gradle
```
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
            force 'com.google.firebase:firebase-common:17.0.0'
            force 'com.google.firebase:firebase-iid:16.0.0'
            force 'com.google.firebase:firebase-auth:17.0.0'
            force 'com.facebook.react:react-native:0.66.4'
            force 'androidx.annotation:annotation:1.6.0-beta01'
            force 'com.ironsource.sdk:mediationsdk:7.2.7'
            force 'org.webkit:android-jsc:r250230'
            force "org.jetbrains.kotlin:kotlin-stdlib:${kotlin_version}"
            force "org.jetbrains.kotlin:kotlin-stdlib-common:${kotlin_version}"
            force "org.jetbrains.kotlin:kotlin-reflect:${kotlin_version}"
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
    "react-native-reanimated": "2.14.4",
    "@react-navigation/drawer": "5.2.0",
    "@react-navigation/native": "^5.9.2",
    "@react-navigation/stack": "^5.14.1",
```

