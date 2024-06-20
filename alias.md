## Creating Git alias

- Format `git config <level> alias.<alias name> '<your sequence of git commands>'`

- ```shell
$ git config --global alias.tree 'log --graph --decorate --pretty=oneline --abbrev-commit'

$ git tree
* b96ce32 (HEAD -> master) added newfile
* 1ff47d2 added another file - newfile.txt
* c3f1349 2nd commit using git commit command
* 85c1969 first commit
      