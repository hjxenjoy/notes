# Package.json file starter

Something todo after create-react-app project.

## Install typescript

```sh
yarn add -D typescript
```

because

```sh
warning "react-scripts > @typescript-eslint/eslint-plugin@1.6.0" has unmet peer dependency "typescript@*".
warning "react-scripts > @typescript-eslint/parser@1.6.0" has unmet peer dependency "typescript@*".
warning "react-scripts > @typescript-eslint/eslint-plugin > @typescript-eslint/typescript-estree@1.6.0" has unmet peer dependency "typescript@*".
warning "react-scripts > @typescript-eslint/eslint-plugin > tsutils@3.14.0" has unmet peer dependency "typescript@>=2.8.0 || >= 3.2.0-dev || >= 3.3.0-dev || >= 3.4.0-dev || >= 3.5.0-dev || >= 3.6.0-dev".
```

## Install eslint and prettier

```sh
yarn add -D eslint eslint-config-airbnb eslint-config-prettier eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-prettier eslint-plugin-react prettier
```

## Install commitizen and husky

```sh
# for git cz command
npm install --global commitizen
yarn add -D cz-conventional-changelog husky lint-staged
# for custom commitizen config
yarn add -D cz-customizable
```

* Add package config

```json
{
  "lint-staged": {
    "src/**/*.{js,jsx,ts,tsx,json}": [
      "eslint --fix",
      "git add"
    ]
  },
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "config": {
    "commitizen": {
      "path": "node_modules/cz-conventional-changelog"
    }
  },
}
```

* Add custom commitizen config

```json
{
  "config": {
    "commitizen": {
      "path": "node_modules/cz-customizable"
    },
    "cz-customizable": {
      "config": "your/cz/config/path.js"
    }
  },
}
```

## Install Dev Proxy

```sh
yarn add http-proxy-middleware
```

Add setupProxy.js

```js
const proxy = require('http-proxy-middleware')

const { DEV_PROXY } = process.env

module.exports = app => {
  app.use(
    proxy('/api', {
      target: DEV_PROXY,
      changeOrigin: true,
    })
  )
}
```

## Install Sass Support

```sh
yarn add -D sass node-sass
```

## Install Basic Dependencies

```sh
yarn add axios classnames prop-types query-string react-helmet react-router react-router-config react-router-dom
```

## Add some dotfiles, config and basic component

```
.babelrc
.editorconfig
.eslintignore
.eslintrc
.prettierrc
```
