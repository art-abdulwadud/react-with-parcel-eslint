# Setting up react with parcel bundler and eslint

```
yarn init
```

```
yarn add parcel-bundler eslint -D
```

```
yarn add react react-dom
```

```
yarn add @babel/core@7.9.6 @babel/preset-react @babel/plugin-proposal-class-properties @babel/preset-env -D
```

create .babelrc file and add

```javascript
{
  "presets":["@babel/preset-react", "@babel/preset-env"],
  "plugins":["@babel/plugin-proposal-class-properties"]
}
```

As for eslint, create .eslintrc.js file, make sure to add this so that you don't get errors on react syntax with eslint

```javascript
module.exports = {
  env: {
    browser: true,
    es6: true,
    node: true,
    jest: true
  },
  plugins: ['react'],
  extends: ['airbnb-base', 'eslint:all', 'plugin:react/recommended'],
  parser: 'babel-eslint',
  globals: {
    Atomics: 'readonly',
    SharedArrayBuffer: 'readonly'
  },
  settings: {
    react: {
      createClass: 'createReactClass',
      pragma: 'React',
      version: 'detect',
      flowVersion: '0.53'
    }
  },
  parserOptions: {
    ecmaVersion: 2018,
    sourceType: 'module',
    ecmaFeatures: {
      jsx: true
    }
  },
  rules: {
    'comma-dangle': ['error', 'never'],
    'no-param-reassign': ['error', { props: false }],
    'class-methods-use-this': 0
  }
};
```

Good to go, create a react component e.g

```javascript
import React, { Component } from 'react';
import ReactDOM from 'react-dom';

class App extends Component {
  render() {
    return (
      <div>
        <h1>Find these files in the link description below</h1>
      </div>
    );
  }
}

ReactDOM.render(<App />, document.getElementById('root'));
```

Add scripts to package.json file

```javascript
"scripts": {
    "start": "parcel src/index.html",
    "build": "parcel build src/index.html"
  },
```

Start server

```
yarn start
```
