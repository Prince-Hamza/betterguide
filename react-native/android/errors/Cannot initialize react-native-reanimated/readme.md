


#### Add packages according to version compatibility

```
yarn add react-native@0.66.4 
```

```
yarn add react-native-reanimated@2.14.4
```

#### Add this to babel.config.js in project root

```
module.exports = {
  presets: ['module:metro-react-native-babel-preset'],
  plugins: ['react-native-reanimated/plugin']
};

```


