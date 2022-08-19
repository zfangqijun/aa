git ssh 代理

如果走的是ssh，需要设置ssh代理

1、https访问
```
git config --global http.https://github.com.proxy socks5://127.0.0.1:1086
```

设置完成后, ~/.gitconfig文件中会增加以下条目:
```
[http "https://github.com"]
    proxy = socks5://127.0.0.1:1086
```

2、ssh访问
需要修改~/.ssh/config文件, 没有的话新建一个. 同样仅为github.com设置代理:
```
Host github.com
    User git
    ProxyCommand nc -v -x 127.0.0.1:1086 %h %p
```
