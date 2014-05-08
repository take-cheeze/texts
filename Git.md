* Popular source code management system.
* Was born in Linux community and spread by [Github](https://github.com/)
* [How to disappear completely and never be found.](http://d.hatena.ne.jp/ichhi/20110825/1314300975)
* [zsh setting](http://qiita.com/items/8d5a627d773758dd8078)
* [svn2github mirroring](http://svn2github.com/)
* [subtree merge instruction](https://help.github.com/articles/working-with-subtree-merge)

## magit
* Best git-mode on Emacs.
* [keybindings](http://orthogonal.me/2012/06/23/magit-keybindings/)
* 'E': run rebase -i

## github
* popular git hosting service
* [issue to pull request](http://stackoverflow.com/questions/4528869/how-do-you-attach-a-new-pull-request-to-an-existing-issue-on-github)
  * needs to use API
* [searching inside repository](http://stackoverflow.com/questions/3616221/search-code-inside-a-github-project)
  * repo:author/name
* [GitHub PubSubHubbub hooks](http://unknownplace.org/memo/2012/08/08/1/)
* [changing root directory](http://stackoverflow.com/questions/11764003/change-the-root-directory-of-a-git-repository)

## Commands

## subtree
* [document](https://github.com/git/git/blob/master/contrib/subtree/git-subtree.txt)
* used to import external repository with prefix
* [article about submodule vs subtree](http://blogs.atlassian.com/2013/05/alternatives-to-git-submodule-git-subtree/)
* easier than submodule since not initialization is needed

### status
* run this command before any git operation.

### reset
* use to revert codes.
* "git reset HEAD^1" is useful to change the recent history.

### checkout
* use to switch branches and clear repository.

### branch
* branch managing command

### stash
* use to save and pop temporary edit or crossing over branch.
* git stash save
  * save current changes
* git stash pop
  * pop saved stash

## remote
* [Deleting branch that can't be deleted by pusing :branch.](http://www.darkcoding.net/software/cleaning-up-old-git-branches/)
  * Use 'prune'.

### push/pull
* use for merging and publishing to external repository.
* [deleting remote branch](http://at-aka.blogspot.jp/2010/06/git.html)
  * git push remote_name :deleting_branch
* 'pull' is harmful so use fetch instead.

### commit
* use to make commit
* don't forget to check that code compiles correctly before this.
* "-a" option is useful but make sure all code can be committed.

### config
* [Document](http://www.kernel.org/pub/software/scm/git/docs/git-config.html)
* Repository configuring.
* for global setting use ~/.gitconfig

## Attribute
* [Document](http://www.kernel.org/pub/software/scm/git/docs/gitattributes.html)
* Indent setting is useful.