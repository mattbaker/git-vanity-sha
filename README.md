# git-vanity-sha

This is a Very Good Program inspired by this [tweet](https://mobile.twitter.com/leinweber/status/989415433605283840).

<img width=400 src="https://i.imgur.com/PmG9jZZ.png">

Add `git-vanity-sha` to your `$PATH` and try it out:

```
🦋  git commit -m "light re-org"
[master 909939a] light re-org
 1 file changed, 12 insertions(+), 8 deletions(-)

1Q84» ~/dev/git-dead 🌱  master
🦋  git vanity-sha cafe
SHA found: cafe7f7fe2054aa79dd6f5e1f994242b70cd7572
Change committer timestamp to 2018-04-27 00:31:18 -0700? This will amend your commit.
(y/n): y

-----------------------------------------------
commit cafe7f7fe2054aa79dd6f5e1f994242b70cd7572
Author: Matt Baker <mbaker.pdx@gmail.com>

    light re-org
```
