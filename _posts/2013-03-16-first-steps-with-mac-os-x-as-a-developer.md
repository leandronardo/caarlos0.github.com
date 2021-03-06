---
layout: post
title: "First steps with Mac OS X as a Developer"
---

So, I just bought my first Mac, and decided to wrote this in order to help
others =)

As a developer, the 3 apps I use most: Terminal, Text Editor and Music Player.
So, in the mac-brave-new-world, I particularly use, in order: The default
Terminal.app, SublimeText2 and iTunes.

<img src="http://cl.ly/image/1n45013K0V17/Captura%20de%20Tela%202013-03-16%20%C3%A0s%2018.01.29.png"
class="noshadow" title="Mac OS X Terminal.app">

SublimeText has his own tips, and I won't write about that. The web is already
full of them. Go to the wild-web and find the best for you.

I will focus in terminal tools and other things. Also, I have a jocke about that:

> A man who calls himself as a developer says: "I'm a developer, I don't want
to write commands, I just want to use some UI to do what I want to".

Yep, this is a joke. _(before it was sad)_

Well, let's stop this and go to what really matter.

## First things first

Install [XCode command line tools][1]. You will always need it anyway.

## Install Homebrew

[Homebrew][2] is some kind of _ports_ for Mac. As a developer, you should
install it:

{% highlight bash %}
ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"
{% endhighlight %}

So, to install, for example, git:

{% highlight bash %}
brew install git
{% endhighlight %}

Yep, that easy.

## Install git

> (read the example given in previous item :smile: )

## Install zsh

[ZSH][3] is a pretty powerful shell for *nix systems. As a developer, it just
changed my life. I don't even know how I lived before using it. No, really,
install it NOW:

{% highlight bash %}
brew install zsh
chsh /bin/zsh
{% endhighlight %}

## Use some dotfiles

ZSH is pretty powerful and highly customizable. There are a lot of projects
around the web to achieve an easy start to it.

Some examples:

- [oh-my-zsh][4]
- [holman/dotfiles][5]
- my dotfiles for [linux][6] and [osx][7]

I've [already wrote about this before][8], in case you want to read something
about it.

In this example, let's install [my dotfiles for osx][7] (basically, the
holman's with some custom things):

{% highlight bash %}
git clone  https://github.com/caarlos0/dotfiles-mac ~/.dotfiles
cd ~/.dotfiles
script/bootstrap
source ~/.zshrc
dot # will install some tools and do some basic setup
{% endhighlight %}

And you should be ready to go.

## Install rbenv

[rbenv][9] is a ~lightweight~ ruby vm manager. Basically, it does the same thing
as RVM, but I found it a little bit less intrusive. If you want, you can install
it with brew:

{% highlight bash %}
brew install rbenv ruby-build
rbenv install 2.0.0-p195
rbenv global 2.0.0-p195
rbenv rehash
{% endhighlight %}

Be sure to check your `~/.{zsh,bash}rc` file

## Install hub

[hub][10] is a github command line tool written in Ruby to improve your
git/github diary use. You can install it with `brew`:

{% highlight bash %}
brew install hub
{% endhighlight %}

Example usage:

{% highlight bash %}
hub clone caarlos0/up
{% endhighlight %}

Much less typing, IMHO =)


## Install RMagick gem without pain

So, in some projects I use the `rmagick` gem, and it got me some headache to
install.

Well, here the steps:

{% highlight bash %}
brew install imagemagick
brew install pkg-config
C_INCLUDE_PATH=/usr/local/Cellar/imagemagick/6.8.0-10/include/ImageMagick gem install rmagick
{% endhighlight %}

And boom! It works =) Pretty tricky.

**Update:** The `C_INCLUDE` trick seems to not be needed anymore.

## Other tips:

- Everyone likes Emojis. Take this [cheat sheet][11];
- [Disk Inventory X][14], a very good disk analysis tool;
- [Hidden OSX Features, tips and tricks][16];
- [SizeUP][17], a window tilling manager for OSX.

If you want, you can also take a look at my [OSX Settings][15], which
is already available in my dotfiles (and you already have if you ran the
`dot` script).

As suggested in comments and by some friends:

- Install [iTerm2][12], a cool Terminal.app replacement;
- Install [Alfred][13], a produtivity tool.

****

Have your own tips? Share with the other fellows in comment box bellow.

Cheers!


[1]: https://developer.apple.com/devcenter/mac/index.action
[2]: http://mxcl.github.com/homebrew/
[3]: http://www.zsh.org/
[4]: https://github.com/robbyrussell/oh-my-zsh
[5]: https://github.com/holman/dotfiles/
[6]: https://github.com/caarlos0/dotfiles-linux
[7]: https://github.com/caarlos0/dotfiles-osx
[8]: /posts/dotfiles-are-meant-to-be-forked/
[9]: https://github.com/sstephenson/rbenv/
[10]: https://github.com/defunkt/hub
[11]: http://www.emoji-cheat-sheet.com
[12]: http://www.iterm2.com/
[13]: http://www.alfredapp.com/
[14]: http://www.derlien.com/
[15]: https://github.com/caarlos0/dotfiles-mac/blob/master/osx/set-defaults.sh
[16]: http://apple.stackexchange.com/questions/400/please-share-your-hidden-os-x-features-or-tips-and-tricks
[17]: www.irradiatedsoftware.com/sizeup/

