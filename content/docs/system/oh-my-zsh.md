---
title: "安装配置oh-my-zsh"
linkTitle: "oh-my-zsh"
weight: 201
date: 2021-05-10
description: >
  安装配置oh-my-zsh
---

## 介绍

zsh的功能极其强大，只是配置过于复杂，起初只有极客才在用。后来，一些极客为了让更多人受益，开发了Oh-my-zsh这个插件，用来简化zsh的配置，让zsh更加容易上手。

官网地址：

https://github.com/ohmyzsh/ohmyzsh

## 安装

参考 https://github.com/ohmyzsh/ohmyzsh#basic-installation ：

```bash
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

安装完成之后，`.zshrc` 的内容会被 oh-my-zsh 替换，原有的内容会被备份到文件 `.zshrc.pre-oh-my-zsh` 中。因此如果之前在 `.zshrc`  中有设置内容，则需要手工移过来。

## 配置

### 关闭自动粘贴转义

Oh-my-zsh 默认开启自动粘贴转义，容易造成问题，建议关闭：

```bash
# Uncomment the following line if pasting URLs and other text is messed up.
# 把这里的注释取消即可
DISABLE_MAGIC_FUNCTIONS="true"
```

### 配置插件

https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins

Oh-my-zsh 默认将插件存放在 `~/.oh-my-zsh/plugins` 目录下，数量非常多：

```bash
➜  .oh-my-zsh git:(master) cd plugins 
➜  plugins git:(master) ls
adb                      git-flow                 powify
alias-finder             git-flow-avh             profiles
ansible                  git-hubflow              pyenv
ant                      git-lfs                  pylint
apache2-macports         git-prompt               python
arcanist                 gitfast                  rails
archlinux                github                   rake
asdf                     gitignore                rake-fast
autoenv                  glassfish                rand-quote
autojump                 globalias                rbenv
autopep8                 gnu-utils                rbfu
aws                      go                       react-native
battery                  golang                   rebar
bazel                    gpg-agent                redis-cli
bbedit                   gradle                   repo
bgnotify                 grails                   ripgrep
boot2docker              grc                      ros
bower                    grunt                    rsync
branch                   gulp                     ruby
brew                     hanami                   rust
bundler                  helm                     rustup
cabal                    heroku                   rvm
cake                     history                  safe-paste
cakephp3                 history-substring-search salt
capistrano               hitchhiker               sbt
cargo                    hitokoto                 scala
cask                     homestead                scd
catimg                   httpie                   screen
celery                   ionic                    scw
chruby                   ipfs                     sdk
chucknorris              iterm2                   sfdx
cloudapp                 jake-node                sfffe
cloudfoundry             jenv                     shell-proxy
codeclimate              jfrog                    shrink-path
coffee                   jhbuild                  singlechar
colemak                  jira                     spring
colored-man-pages        jruby                    sprunge
colorize                 jsontools                ssh-agent
command-not-found        jump                     stack
common-aliases           kate                     sublime
compleat                 keychain                 sublime-merge
composer                 kitchen                  sudo
copybuffer               knife                    supervisor
copydir                  knife_ssh                suse
copyfile                 kops                     svcat
cp                       kube-ps1                 svn
cpanm                    kubectl                  svn-fast-info
dash                     lando                    swiftpm
debian                   laravel                  symfony
deno                     laravel4                 symfony2
dircycle                 laravel5                 systemadmin
direnv                   last-working-dir         systemd
dirhistory               lein                     taskwarrior
dirpersist               lighthouse               term_tab
django                   lol                      terminitor
dnf                      lxd                      terraform
dnote                    macports                 textastic
docker                   magic-enter              textmate
docker-compose           man                      thefuck
docker-machine           marked2                  themes
doctl                    mercurial                thor
dotenv                   meteor                   tig
dotnet                   microk8s                 timer
droplr                   minikube                 tmux
drush                    mix                      tmux-cssh
eecms                    mix-fast                 tmuxinator
emacs                    mongocli                 torrent
ember-cli                mosh                     transfer
emoji                    mvn                      tugboat
emoji-clock              mysql-macports           ubuntu
emotty                   n98-magerun              ufw
encode64                 nanoc                    universalarchive
extract                  ng                       urltools
fabric                   nmap                     vagrant
fancy-ctrl-z             node                     vagrant-prompt
fasd                     nomad                    vault
fastfile                 npm                      vi-mode
fbterm                   npx                      vim-interaction
fd                       nvm                      virtualenv
fedora                   oc                       virtualenvwrapper
firewalld                osx                      vscode
flutter                  otp                      vundle
forklift                 pass                     wakeonlan
fossil                   paver                    wd
frontend-search          pep8                     web-search
fzf                      per-directory-history    wp-cli
gas                      percol                   xcode
gatsby                   perl                     yarn
gb                       perms                    yii
gcloud                   phing                    yii2
geeknote                 pip                      yum
gem                      pipenv                   z
genpass                  pj                       zbell
gh                       please                   zeus
git                      pod                      zsh-interactive-cd
git-auto-fetch           postgres                 zsh-navigation-tools
git-escape-magic         pow                      zsh_reload
git-extras               powder
```



#### git

默认git插件是已经启动的:

```bash
plugins=(git)
```

#### brew

plugins=(... brew)

#### docker

Docker 相关的三个命令 docker docker-compose docker-machine 都是支持的：

```bash
plugins=(... docker docker-compose docker-machine)
```

#### kubectl

```bash
plugins=(... kubectl)
```

比较神奇的是： k 这个 alias 居然可以直接用，而且自动完成也是OK的。

#### 小结

最后启动的插件如下琐事

```
plugins=(git golang brew docker kubectl rust rustup npm mvn node)
```

### 配置样式

https://github.com/ohmyzsh/ohmyzsh/wiki/Themes

暂时先用默认。

## 参考资料


- [Linux/Mac如何配置zsh并使用Oh-my-zsh？让你的终端更加好用](https://www.mintimate.cn/2021/02/05/configZsh/)
- [Oh My Zsh, 『 安装 & 配置 』](https://zhuanlan.zhihu.com/p/35283688)
- [常用的oh-my-zsh插件](https://zhuanlan.zhihu.com/p/61447507)
