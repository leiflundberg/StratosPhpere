A suggested Vagrantfile for the StratosPhpere dev environment and a good starting point. Feel free to tweak it as you see fit.

If you run into synced folder trouble between Windows 10 host and CentOS 7 guest:
https://stackoverflow.com/questions/40972345/vagrant-synced-folders-not-working-real-time-on-virtualbox

For nicer directory colors when using shared folders you can run: 

```
wget https://raw.github.com/trapd00r/LS_COLORS/master/LS_COLORS -O $HOME/.dircolors
echo 'eval $(dircolors -b $HOME/.dircolors)' >> $HOME/.bashrc
. $HOME/.bashrc
```

