# Commit convetion 🎡

Checks if your commit messages meet the conventional commit format. It Helps either you or your team become more productive.

## How to use 🤔

**Installing Dev Dependencies**

Using yarn
```bash
yarn add -D husky cz-conventional-changelog @commitlint/config-conventional @commitlint/cli
```

Using npm
```bash
npm install -D husky cz-conventional-changelog @commitlint/config-conventional @commitlint/cli
```

**Create a commitlint config file on you root folder structure**
```bash
touch commitlint.config.js
```

Insert the following code below into the file
```json
module.exports = {
    extends: ['@commitlint/config-conventional']
}
```

**Configuring your package.json**

Add husky config in order to trigger for commit messages

```json
  "husky": {
    "hooks": {
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS",
      "prepare-commit-msg": "exec < /dev/tty && git cz --hook || true"
    }
  },
```

Add your commitizen path

```json
  "config": {
    "commitizen": {
      "path": "./node_modules/cz-conventional-changelog"
    }
  }
```

Add a script for an easy cli command

```json
  "scripts": {
    "commit": "git-cz",
  },
```

Your package.json should be like this 👇
```json
{
  "name": "commit-convention",
  "version": "1.0.0",
  "main": "index.js",
  "license": "MIT",
  "husky": {
    "hooks": {
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS",
      "prepare-commit-msg": "exec < /dev/tty && git cz --hook || true"
    }
  },
  "scripts": {
    "commit": "git-cz",
  },
  "devDependencies": {
    "@commitlint/cli": "^11.0.0",
    "@commitlint/config-conventional": "^11.0.0",
    "@types/express": "^4.17.9",
    "cz-conventional-changelog": "^3.3.0",
    "husky": "^4.3.6",
    "ts-node-dev": "^1.0.0",
    "typescript": "^4.1.2"
  },
  "config": {
    "commitizen": {
      "path": "./node_modules/cz-conventional-changelog"
    }
  }
}
```

### Happy Hacking 💻

<h1 align="center"> 
  <img alt="commitlint gif" src="./assets/commit-convention.gif" width="800px"/>
</h1>

