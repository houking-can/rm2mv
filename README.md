# rm2mv
Replace linux command rm with mv for bash and zsh

### Bash

```
export TRASH=/data/rubbish/
alias rm=trash
alias rl='ls $TRASH'
alias ur=undelfile
undelfile()
{
   mv $TRASH/$@ ./
}
trash()
{
  if [ ! -d $TRASH  ];then
      mkdir $TRASH
  fi
  mv $@ $TRASH
}
cleartrash()
{
    read -p "Clear sure?[n/y]" confirm
    [ $confirm == 'y' ] || [ $confirm == 'Y' ]  && /bin/rm -rf $TRASH/*
}
qrm()
{
    read  "confirm?Clean sure[n/y]"
    [ $confirm = 'y' ] || [ $confirm = 'Y' ]  && /bin/rm -rf $@
}
```



### Zsh

```
export TRASH=/data/rubbish/
alias rm=trash
alias rl='ls $TRASH'
alias ur=undelfile
undelfile()
{
   mv $TRASH/$@ ./
}
trash()
{
  if [ ! -d $TRASH  ];then
      mkdir $TRASH
  fi
  mv $@ $TRASH
}
cleartrash()
{
    read  "confirm?Clean sure[n/y]"
    [ $confirm = 'y' ] || [ $confirm = 'Y' ]  && /bin/rm -rf $TRASH/*
}
qrm()
{
    read  "confirm?Clean sure[n/y]"
    [ $confirm = 'y' ] || [ $confirm = 'Y' ]  && /bin/rm -rf $@
}
```

### Note

The main difference is in the function **cleartrash** as  there are some difference of **read** command between bash and zsh
