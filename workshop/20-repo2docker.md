# repo2docker - the tool behind BinderHub

The tool used to construct the docker image that is launched is called
`repo2docker`. It is a standalone tool you can use locally independent of
your desire to share your work.

If you have docker installed on your laptop you can use `repo2docker`. Install
it by running:
```
pip install https://github.com/jupyter/repo2docker/archive/master.zip
```

> Note: we are a bit behind making releases for repo2docker but the latest
> version from the repository is used on mybinder.org so it should be fine
> to install `master`.

Once it is installed you can try out repositories that contain files `repo2docker`
recognises to construct docker images locally:

```
repo2docker https://github.com/norvig/pytudes/
```

This will build https://github.com/norvig/pytudes/. What you see printed on your
console is very similar to what you would see in the build log output on the
mybinder.org website.

The first time you run this it will take quite a while.

It will eventually print something like:
```
[C 12:22:33.482 NotebookApp]

    Copy/paste this URL into your browser when you connect for the first time,
    to login with a token:
        http://0.0.0.0:57184/?token=80b9438886c25d3da7f519823284a4e2c63800669e76e605
```

If you open the link printed here in your browser you will see the familiar
notebook interface.

## repo2docker for local repositories

`repo2docker` can build container from any source that `git` understands. This
means that you can use it with git repositories stored on your laptop, GitLab,
Bitbucket, etc.

To do:
1. clone your https://github.com/<YOURGITHUBNAME>/my-first-binder repository
  onto your laptop
1. then run `repo2docker <path-to-your-local-copy>`

The advantage of running `repo2docker` locally is that you can edit files
using your favourite editor, save changes and make commits. From within
your local clone of your GitHub repository:

1. run `repo2docker -v .:/home/$USER .`
1. open the URL printed at the end
1. use your favourite editor to create a new file in the repository
1. check in your browser to see the new file

Using `repo2docker` locally means you can start using it to handle installing
software that you can not handle via a Python virtualenv, conda environment,
or for languages like R that do not have the equivalent of virtual environments.
