  ```
  mkdir ~/npm
  export PATH=~/npm/bin:$PATH //.bashrc
  //下载nodejs，解压缩至node目录
  cd node/bin
  ./node -v   //查看node版本
  //建立软链接
  sudo ln -s /home/chen/node/bin/node /usr/bin/node

  
  
  prefix = /home/chen/npm
  npm config set registry https://registry.npm.taobao.org/
  npm config set loglevel http
  npm config set progress false



  sudo apt-get install git  
  git config --global user.name chenzhutao
  git config --global user.email 1248378683@qq.com
  git config --global push.default simple
  git config --global core.quotepath false 
  git config --global core.editor "vim"
  ssh-keygen -t rsa -b 4096 -C "1248378683@qq.com"
  cat ~/.ssh/id_rsa.pub
  ssh -T git@github.com

  sudo apt-get install python-pip
  pip install git+https://github.com/shadowsocks/shadowsocks.git@master

  {
    "server":"207.148.94.164",
    "server_port":1984,
    "local_address": "127.0.0.1",
    "local_port":1080,
    "password":"????",
    "timeout":300,
    "method":"aes-256-cfb",
    "fast_open": false
}

```
