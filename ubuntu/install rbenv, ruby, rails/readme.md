```
sudo apt update
```


```
sudo apt install git curl libssl-dev libreadline-dev zlib1g-dev autoconf bison build-essential libyaml-dev libreadline-dev libncurses5-dev libffi-dev libgdbm-dev
```


```
curl -fsSL https://github.com/rbenv/rbenv-installer/raw/HEAD/bin/rbenv-installer | bash
```


```
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
```



```
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
```



```
source ~/.bashrc
```



```
rbenv --version
```

```
rbenv install -l
```


```
rbenv install 2.7.6
```

```
ruby -v
```


```
echo "gem: --no-document" > ~/.gemrc
```

```
gem install bundler
```


```
gem env home
```


latest version

```
gem install rails
```

or a specific version

```
gem install rails -v 6.1.4.1
```


