####  install yarn
```
npm install -g yarn
```

#### add eslint parser dependency 
```
yarn add @babel/eslint-parser
```

above two steps might be optional depending on vs code settings


####  create file eslintrc.json in root
####  copy paste following json

```
{
    "parserOptions": {
        "ecmaVersion": 2021,
        "ecmaFeatures": {
            "jsx": true,
            "js": true
        },
        "sourceType": "module"
    },
    "env": {
        "node": true,
        "browser": true
    },
    "globals": {
        "__DEV__": true,
        "__CLIENT__": true,
        "__SERVER__": true,
    },
    "settings": {
        "react": {
            "version": "detect"
        }
    },
    "plugins": [
        "react",
        "react-hooks"
    ],
    "rules": {
        "react/jsx-no-bind": [
            "error",
            {
                "allowArrowFunctions": true,
                "allowBind": false,
                "ignoreRefs": true
            }
        ],
        "no-undef": "error",
        "react/no-did-update-set-state": "error",
        "react/no-unknown-property": "error",
        "react/no-unused-prop-types": "error",
        "react/prop-types": "off",
        "react/react-in-jsx-scope": "error",
        "react-hooks/rules-of-hooks": "error",
        "react-hooks/exhaustive-deps": "off"
    }
}
```



#### minimum vs code settings 
```
{
    "workbench.colorTheme": "Default Dark+",
    "files.autoSave": "afterDelay",
    "eslint.enable": true
}
```
eslint is believed to be enabled by default
