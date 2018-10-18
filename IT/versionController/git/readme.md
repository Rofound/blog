#

## Permission denied (publickey)
- https://www.cnblogs.com/wmr95/p/7852832.html
- git config --global user.name "Rofound"
- git config --global user.email "1353590214@qq.com"
- ssh-add ~/.ssh/id_rsa
- eval `ssh-agent -s`
- ssh-add ~/.ssh/id_rsa
- ssh -T git@github.com

## 