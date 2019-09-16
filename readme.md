A suggested Vagrantfile for the StratosPhpere dev environment and a good starting point. Feel free to tweak it as you see fit.

For nicer directory colors when using shared folders you can run: 

wget https://raw.github.com/trapd00r/LS_COLORS/master/LS_COLORS -O $HOME/.dircolors
echo 'eval $(dircolors -b $HOME/.dircolors)' >> $HOME/.bashrc
. $HOME/.bashrc
