
# CSource

Source env vars from a file encrypted with [ccrypt](https://ccrypt.sourceforge.net/).

Only works on linux, as far as I can tell. 

## How to use

Write your environment variables into a `.env` file as normal:

```sh
export EXAMPLE=test
```

Encrypt the file with ccrypt:

```sh
cccrypt example.env
```

when you want to load the variables into your current shell, run 

```sh
. csource example.env.cpt
```

The environment variables you have configured are now loaded into your shell, but the file is still encrypted. 

The example here has a decryption key of `test`


## Motivation

I often use environment variables to store secrets. But I do not want to leave these secrets un encrypted on disk.

`csource` is an extremely simple way to keep the file of environment variables encrypted, while making it fairly easy to use them in development work.


## Installation

You can make it easy to run `csource` by adding it to your $PATH or creating a symbolic link to it in `$HOME/.local/bin`. 


## How it works

The whole thing is:

```sh

source <(ccat $1)

```

## A better version?

I bet there are much better ways to do this. If you come across this project and know of something better, let me know!

Also we're sourcing twice - is that necessary?
