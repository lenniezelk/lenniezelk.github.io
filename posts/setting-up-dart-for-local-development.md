<!--
.. title: Setting up Dart for local development
.. slug: setting-up-dart-for-local-development
.. date: 2019-05-28 11:23:34 UTC+03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->

I've been learning Flutter for mobile development lately. I like the journey so far and I'm going to be posting stuff I learn along the way. First i'll show how to setup Dart for local development. I use `asdf` for managing different versions of language runtimes on my local machine. I found out about it when trying to setup different Python versions. My dev machine comes with Python 3.7 but at work we use Python 3.6 and I like having the exact version in use. What to do? `asdf` to the rescue. `asdf` has a plugin system that allows allows the installation of different langauge runtimes for example you can install Python 3.5, 3.6 and 3.8 on the same machine and switch between them. A lot of langauges are supported you can find these [here](https://asdf-vm.com/#/plugins-all).

To setup `asdf` run:

```
#!shell
git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.7.2`
```

Replace `0.7.2` with the latest version which you can find [here](https://github.com/asdf-vm/asdf/releases). Next add `asdf` to your shell like so:

```
#!shell
echo -e '\n. $HOME/.asdf/asdf.sh' >> ~/.zshrc
echo -e '\n. $HOME/.asdf/completions/asdf.bash' >> ~/.zshrc
```

Remember to replace `.zshrc` with your shell specific config file e.g .bashrc. Reload your config file `source .zshrc`. You are good to go.

Now lets setup dart. We begin by installing the dart plugin:

```
#!shell
asdf plugin-add dart
```

Now we can install dart sdk and tools by running:

```
#!shell
asdf install dart 2.3.1
```

Replace 3.2.1 with the latest version or the version you want. You can find these [here](https://github.com/dart-lang/sdk/releases). You need to choose a global version. This is the version that will be run when you type `dart` in any shell. You can do this by:

```
#!shell
asdf global dart 2.3.1
```

You can also set a version to be used only in the current shell:

```
#!shell
asdf local dart 2.3.1
```

Happy darting.
