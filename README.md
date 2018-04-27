# git vanity-sha

This is a Very Good Program inspired by this [tweet](https://mobile.twitter.com/leinweber/status/989415433605283840).

<p align="center">
<img width=400 src="https://i.imgur.com/PmG9jZZ.png">
</p>

He wasn't joking.

<p align="center">
<img width=400 src="https://i.imgur.com/hMM9H2N.png">
</p>

So I thought maybe I'd just write a program to do it.

`git vanity-sha` will try its darndest to tweak the commiter timestamp of your last commit to produce a commit SHA using the hexadecimal prefix you supply.

```plaintext
$ git commit -am "refactor warp core"
[master 909939a] refactor warp core
 1 file changed, 12 insertions(+), 8 deletions(-)

$ git vanity-sha cafe
Searching for new SHA...

SHA found: cafe7f7fe2054aa79dd6f5e1f994242b70cd7572
Change committer timestamp to 2018-04-27 00:31:18 -0700? This will amend your commit.
(y/n): y

-----------------------------------------------
commit cafe7f7fe2054aa79dd6f5e1f994242b70cd7572
Author: Matt Baker <matt@example.com>

refactor warp core
```

Now you can amend a commit to have a quirky prefix whenever you want except for when `git-vanity-sha` doesn't find one.

## Installation

Grab the `git-vanity-sha` script and stick it in your path somewhere. Make sure you `chmod +x` it, and `hash -r`.

Now you can say `git vanity-sha beef` in your repo.

## Frequently Asked Questions

### How does it work?

`git vanity-sha` will attempt to find a commit SHA starting with the hex prefix you specify by applying a delta to the committer timestamp of your last commit. It starts off making small changes to the timestamp (a few seconds) and gets bigger as it searches (up to several days). 

If it finds a timestamp that will cause your commit's SHA to have the target prefix, it will give you the option to amend that commit or abort the process.

### Is this a good idea?

Absolutely not.

### Will this mess something up?

Probably.

### Will you help me if something goes wrong?

If you are worried something could go wrong while using this then you are both practical and a person who should not use this program.

### It didn't find a SHA with the prefix I wanted :(

If you're really determined, then change `TIMESTAMP_DELTA_MAX` to a huge number and go for a walk and maybe you'll get lucky.
