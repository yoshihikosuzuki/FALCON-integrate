# FALCON-integrate + minialign
This is a place to coordinate FALCON builds and tests.

* **Use fc_run.cfg as a template of the config file for minialign mode (instead of FALCON-example/run/*)**

## Recommended example of a series of commands for usage

```
$ git clone --recursive https://github.com/yoshihikosuzuki/FALCON-integrate
$ cd FALCON-integrate
$ git submodule update --init
$ virtualenv fc_env; source fc_env/bin/activate
$ make init
$ source env.sh
$ make config-edit
(manually comment out "PREFIX" in minialign/Makefile)   # TODO: cope with this
$ make -j all
$ fc_run fc_run.cfg   # after edited
```

---

The git-submodules here define a consistent set of revisions.

You may use any system you like for building, testing, and integration,
but we also provide some submodules which can help with that.

## submodules
In case you are unfamiliar with [**git-submodules**](http://www.git-scm.com/book/en/v2/Git-Tools-Submodules), they are quite easy to use from the command-line:
```sh
git submodule update --init
```
If that fails, you can update your **git**, or try this:
```sh
git submodule init
git submodule update
```
which is *almost* the same thing.

## Set-up
You have a few choices:

1. PYTHONUSERBASE
2. virtualenv
3. Standard Python installation

For more details, see the [wiki](https://github.com/PacificBiosciences/FALCON-integrate/wiki).
