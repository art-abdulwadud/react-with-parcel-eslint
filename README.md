# Setting up react with parcel bundler and eslint

## Install 

You can use this as a starter template for react app.

```
git clone 
```

```
yarn
```
After this your are all set up, go ahead and create your components.

## Getting Started 

A breif Tutorial to help you make a template like this from scratch.

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

## License

MIT Copyright (c) 2020 Abdiwadud Mahamad

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
