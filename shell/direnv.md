# direnv - set environment variables specific to a particular directory

There are situations where we want specific environment variables to be set when you enter a particular directory in a shell and want them to be unset when you leave the directory. direnv does just that. For example, it would be useful to set specific aws credentials when entering a particular directory of terraform templates.


### Installation

```shell
$ sudo apt-get install direnv -y

```

Hook direnv to your shell (In my case it is zsh. For more hooks, refer https://direnv.net/docs/hook.html)

```shell
eval "$(direnv hook zsh)"
```

Now create a `.envrc` and put env to be loaded when entering the directory

```shell

$ cd YOUR_DESIRED_DIRECTORY
$ echo export AWS_SECRET_ACCESS_KEY=secret_access_key > .envrc
$ echo export AWS_ACCESS_KEY_ID=access_key_id >> .envrc
```

Now your env variables will be loaded whenever you enter the desired directory and will be unloaded whenever you leave the directory.
