Managing your terminal configuration
====================================

The first thing that you need to do is to identify which shell you are using the
terminal. This tutorial is from the shell `zsh`. `zsh` is a vastly used shell
and the default shell for Mac computers.

To see the shell you are using you need to run the command:

```shell
$ echo $SHELL
```

without the `$`. The symbol `$` is to indicate that this command needs to be run
in the terminal.

If your default shell is not `zsh` then run the command:

```shell
$ chsh -s /bin/zsh
```

Once you have run the command you need to restart (close and open) your terminal
window.

Managing the `zsh` configuration
--------------------------------

Navigate to your home directory by running:

```shell
$ cd
```

Here you want to have a file named `.zshrc`. See if you have the file by running
`ls -a`. If you do not have the file fear not! We will create the file. The
`.zshrc` is the file that keeps all the configurations of your shell.

We will use an open source called Oh My Zsh. It's a framework for managing your
zsh configuration. Run the following command (while again in your home)
directory:

```shell
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

You already can notice difference in your terminal.

Themes
-------

If you open the file `.zshrc` you will see the following line:

```shell
ZSH_THEME="robbyrussell"
```

This is the theme. Choose the theme that you prefer. See
https://github.com/ohmyzsh/ohmyzsh/wiki/Themes.

To see the new theme run:

```shell
$ source .zshrc
```

Autosuggestions
---------------

For autosuggestions run the command:

```shell
$ git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

Then add the plugin to the list of plugins for Oh My Zsh to load (inside `~/.zshrc`):

```shell
plugins=( 
    # other plugins...
    zsh-autosuggestions
)
```

Run:

```shell
$ source .zshrc
```

and now you have autosuggestions! 

Editing `.zshrc`
----------------

To edit the file you can use any editor. If you are in the terminal I recommend
the editor nano.