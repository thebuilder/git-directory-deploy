# git-directory-deploy

[![NPM](https://nodei.co/npm/git-directory-deploy.png)](https://nodei.co/npm/git-directory-deploy/)

Deploy a subdirectory from a git repo to a different branch. Useful to
deploy to [GitHub Pages](https://pages.github.com/).

# Why

The shell script portion of this code is from [X1011/git-directory-deploy](https://github.com/X1011/git-directory-deploy),
and it's best explained in that README:

> Unlike the git-subtree approach, it does not require the generated files be committed to the source branch. It keeps a linear history on the deploy branch and does not make superfluous commits or deploys when the generated files do not change.

This repo accomplishes a few other things:

1) Easier use in Node land
2) Named cli args
3) Publish it to [`npm`](https://www.npmjs.com/) so I can use it as a devDep in projects


# Install

**For global use:**
```sh
npm install -g git-deploy-directory

cd projects/i-want-to-deploy/

git-deploy-directory
```

**Or for use in via [`npm run-script`](https://docs.npmjs.com/cli/run-script):**
```sh
npm install git-deploy-directory --save-dev
```
and then use it in your `package.json` likes this:
```js
"scripts": {
    "deploy": "git-deploy-directory --directory _dist"
}
```


# Usage

###`git-deploy-directory [args]`

#### `--directory [_site]`
The subdirectory to deploy.

#### `--branch [gh-pages]`
The branch that will receive the deploy.

#### `--remote [origin]`
The remote to push the deploy to.

#### `--username [git config user.name || git-directory-deploy]`
The username that will be associated with the deploy commit.

#### `--email [git config user.email]`
The email that will be associated with the deploy commit.

#### `--verbose`
Be louder.

#### `--allow_empty`
Allow the `--directory` to be empty.


### LICENSE

MIT

```
The script at bin/git-directory-deploy.sh is Copyright [Daniel Smith](https://github.com/X1011/git-directory-deploy).
See the file for terms.
```