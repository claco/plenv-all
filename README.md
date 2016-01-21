Provides `plenv all` so that you can run the same code under all of the perl versions you have installed.

Installation
============

Just git clone this repository into a new subdirectory of your plenv plugins directory:

```
git clone https://github.com/claco/plenv-all ~/.plenv/plugins/plenv-all
```

Usage
=====

Just `plenv all <code you want to run>`. For example to run cpanm against all perl versions that you have installed, use:

```
$ plenv all cpanm App::Ack
```

By default plenv all will output a little notification explaining what it is doing for each perl:

```
$ plenv all perl --version
5.20.3>> perl --version

This is perl 5, version 20, subversion 3 (v5.20.3) built for darwin-2level
...

5.22.1>> perl --version

This is perl 5, version 22, subversion 1 (v5.22.1) built for darwin-2level
...
```

To suppress this, pass --bare

```
$ plenv all --bare perl --version
This is perl 5, version 20, subversion 3 (v5.20.3) built for darwin-2level
...

This is perl 5, version 22, subversion 1 (v5.22.1) built for darwin-2level
...
```

By default plenv all will stop on the first failure.

```
$ plenv all perl --vresion
5.20.3>> perl --vresion
Unrecognized switch: --vresion  (-h will show valid options).
```

To suppress this, pass --force

```
$ plenv all --force perl --vresion
5.20.3>> perl --vresion
Unrecognized switch: --vresion  (-h will show valid options).

5.22.1>> perl --vresion
Unrecognized switch: --vresion  (-h will show valid options).
```

Credit
======

This is a fork from the rbenv version of the all command by [Conrad Irwin](https://github.com/ConradIrwin/rbenv-all)
