# Using multiple Github accounts without ssh keys

On my work laptop I want to be able to push to my personal get repos.

There's a good solution using rsa keys, but I dont want those stored on my work computer either.

* https://code.tutsplus.com/tutorials/quick-tip-how-to-work-with-github-and-multiple-accounts--net-22574

## Problem

For particular repos, I want to:

* Be able to override the account being used
* Be prompted for credentials in every push

## Solution

At the root of the repo, set the user for the repo. This will be the display name used in the commits.

```$ git config --local user.name "Your Name"
```

Then set the email address:

```$ git config --local user.email "your@email.com"
```

Next, you will want to make sure that your personal account name is associated with the remote origin for the repo.

```$ git remote set-url origin https://your_user_name@github.com/org/repo
```

Lastly, if you are using a credential helper git will attempt to store your credentials locally.

You can find out from the git config if this is the case. In my case I'm on a Mac which is using the `osxkeychain` helper:

```$ git config --system credential.helper

osxkeychain
```

You can override this beahviour locally has well, to do this edit the `.git/config` file and add the following entry:

```
...
[credential]
    helper=
...
```

And this is it, this last step will prevent the credential helper set at account level to store your credentials locally.
