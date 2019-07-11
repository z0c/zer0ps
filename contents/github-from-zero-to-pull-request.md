# Github: From zero to pull request

6 simple steps on how to contribute to github projects.

Always make sure to read the project's `CONTRIBUTING.md` for contributing guidelines.

1. Fork the repo

Go to the project you want to contribute to and fork the repo.

2. Clone the fork

On your fork, grab the URL to clone.

```
$ git clone <url you copied>
```

3. Add the remote upstream

```
$ git remote add upstream <url of the original repo>
```

The remote upstream represents the original repo. When you clone the fork that, that is your origin. By adding a new remote it allows you to keep in sync with the changes on the original repo by doing:

```
$ git pull upstream master
```

4. Optionally, create a branch to do your work in

You may wish to create a branch so that you can flip between works streams easily or discard if needed

```
$ git checkout -b <feature name>
```

5. Do work

6. Open a pull request

After you have done some commits you can push them to origin:

```
$ git push origin <feature-name>
```

Got to your fork, you should see an option to open the pull request

## Cleaning up a fork

After PR's are merged, you will want to clean up your changes to the upstream so they don't show in subsquent PR's. To do this reset with the upstream

    $ git reset --hard upstream/master
    $ git push origin master --force
