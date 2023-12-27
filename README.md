# gmux


An alternative for tmuxinator



```
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

cd /tmp
wget https://github.com/corvofeng/gmux/releases/download/v0.3.2/gmux_linux_amd64.tar.gz
tar -zxvf gmux_linux_amd64.tar.gz
sudo install -v gmux /usr/local/bin

gmux -p gmux
```


