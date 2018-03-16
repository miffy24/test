  ```
  mkdir ~/npm
  export PATH=~/npm/bin:$PATH //bashrc
  sudo chown -R $USER /usr/local

  prefix = /home/chen/npm
  npm config set registry https://registry.npm.taobao.org/
  npm config set loglevel http
  npm config set progress false




  git config --global user.name chenzhutao
  git config --global user.email 1248378683@qq.com
  git config --global push.default simple
  git config --global core.quotepath false 
  git config --global core.editor "vim"
  ssh-keygen -t rsa -b 4096 -C "1248378683@qq.com"
  cat ~/.ssh/id_rsa.pub
  ssh -T git@github.com



  {
    "server":"207.148.94.164",
    "server_port":1984,
    "local_address": "127.0.0.1",
    "local_port":1080,
    "password":"请发邮件向我询问密码",
    "timeout":300,
    "method":"aes-256-cfb",
    "fast_open": false
}

```
