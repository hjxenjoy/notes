# Package.json file starter

Something todo after create-react-app project.

## Install typescript

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

add package config

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

add custom commitizen config

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
