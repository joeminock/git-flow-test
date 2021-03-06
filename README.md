# README

Creating feature/release/hotfix/support branches
To list/start/finish/delete feature branches, use:
 git flow feature
  git flow feature start <name> [<base>]
  git flow feature finish <name>
  git flow feature delete <name>


For feature branches, the <base> arg must be a branch, when omitted it defaults to the develop branch.
To push/pull a feature branch to the remote repository, use:
 git flow feature publish <name>
  git flow feature track <name>


To list/start/finish/delete release branches, use:
 git flow release
  git flow release start <release> [<base>]
  git flow release finish <release>
  git flow release delete <release>


For release branches, the <base> arg must be a branch, when omitted it defaults to the develop branch.
To list/start/finish/delete hotfix branches, use:
 git flow hotfix
  git flow hotfix start <release> [<base>]
  git flow hotfix finish <release>
  git flow hotfix delete <release>


For hotfix branches, the <base> arg must be a branch, when omitted it defaults to the production branch.
To list/start support branches, use:
 git flow support
  git flow support start <release> <base>


For support branches, the <base> arg must be a branch, when omitted it defaults to the production branch.
Share features with others
You can easily publish a feature you are working on. The reason can be to allow other programmers to work on it or to access it from another machine. The publish/track feature of gitflow simplify the creation of a remote branch and its tracking.
When you want to publish a feature just use:
git flow feature publish <name>


or, if you already are into the feature/<name> branch, just issue:
git flow feature publish


Now if you execute git branch -avv you will see that your branch feature/<name> tracks [origin/feature/<name>]. To track the same remote branch in another clone of the same repository use:
git flow feature track <name>


This will create a local feature feature/<name> that tracks the same remote branch as the original one, that is origin/feature/<name>.
When one developer (depending on your work flow) finishes working on the feature he or she can issue git flow feature finish <name> and this will automatically delete the remote branch. All other developers shall then run:
git flow feature delete <name>


to get rid of the local feature that tracks a remote branch that no more exist.
Using Hooks and Filters
For a wide variety of commands hooks or filters can be called before and after the command.
The files should be placed in .git/hooks
In the directory hooks you can find examples of all the hooks available.
