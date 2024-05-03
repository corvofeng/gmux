# gmux


![629109](https://github.com/corvofeng/gmux/assets/12025071/09293818-40d8-473e-8e6a-aa7b2a790a97)


A Golang version of [tmuxinator](https://github.com/tmuxinator/tmuxinator)

> Most of the code is generated by ChatGPT.

## Installation

```bash
# MacOS
brew install corvofeng/tap/gmux

# Linux -- using bin: https://github.com/marcosnils/bin
bin install https://github.com/corvofeng/gmux ~/usr/bin
# bin ls
# Path           Version  URL                                Status
# ~/usr/bin/gmux  v1.0.1  https://github.com/corvofeng/gmux  OK

# Linux -- using binary
cd /tmp
rm -rfv gmux_linux_amd64.tar.gz
wget https://github.com/corvofeng/gmux/releases/latest/download/gmux_linux_amd64.tar.gz
tar -zxvf gmux_linux_amd64.tar.gz
sudo install -v gmux /usr/local/bin
```

## Usage

### kubeconfig

```bash
ls ~/.kube
cache  pve-kube.config

gmux kube --kube pve-kube.config

# I suggest you add the completion support
#   source <(gmux completion bash)
#   source <(gmux completion zsh)
# or you can add the command into the .bashrc or .zshrc.
gmux kube --kube <tab>
```

[![asciicast](https://asciinema.org/a/657555.svg)](https://asciinema.org/a/657555)


### tmuxinator

```bash
mkdir ~/.tmuxinator

echo '
name: gmux
root: "~/"
windows:
  - p1:
    - ls
    - pwd
  - p2:
    - pwd
    - echo "hello world"
  - p3: htop
' > ~/.tmuxinator/gmux.yml

gmux -p gmux
```
Here is an example:

[![asciicast](https://asciinema.org/a/lVIIOwzWwFAL611IwUeZpohoy.svg)](https://asciinema.org/a/lVIIOwzWwFAL611IwUeZpohoy)


### tmux arg support

You can put the tmux args after the `--`.

```bash
➜  ~ gmux -p gmux -- -V
tmux 3.4

# If -d is specified, any other clients attached to the session are detached.
➜  ~ gmux -p gmux -- at -d
```

