### General message 
You can use the following git commit message template for making commits (# are comments)
```
# (Use the imperative mood and keep it under 50 characters)
# <type>: <short summary>
# Types: feat, fix, docs, style, refactor, test, chore

# <Optional detailed explanation>
# (Wrap lines at ~72 characters, explain what and why, not how)

# <Footer, like issue references>
# e.g., Fixes #123, Closes #456
```

You can create a standard git commit mesasge by saving the above message in a fixed place, e.g. 
```/home/user/Documents/GitMessage/.gitmessage.txt```
Then run the following command: 
```
git config --global commit.template /home/user/Documents/GitMessage/.gitmessage.txt
```
Next time you start writing a commit you have a template to work from.

### Commit message examples
Feature:
```
# The general intend of the commit
Feat: Add pallet detection 

# Optional extra explanation
Added pallet detection to use two sensors instead of one. 
```
Refactor:
```
Refactor: Refactored Pallet class based on codestyle 
```

### Resolving an issue/bug 

When an issue/bug has been resolved you can close the issue by adding 'Fixes #number_of_issue' in the final commit message, this will automatically close the issue on Github. 
You can also close it via Github manually, you can open the link of the issue via [Clickup](#clickup) (see below). 
Do not forget to put the Task in Resolved on [Clickup](#clickup).

### Squash 

Before merging your branch you might want to squash some commits, for example commits that have no valid information should be squashed

rebase the last 3 commits
git rebase -i HEAD~3 

```
pick 402ca26 Feat: Hello world
pick c0a0a3a WiP
pick 3edcde3 Feat: Print hello world 5 times
```

change ```pick``` to ```squash``` or ```s``` of the commits you want to squash

```
pick 402ca26 Feat: Hello world
s c0a0a3a WiP
s 3edcde3 Feat: Print hello world 5 times
```

save the file. <br>
Commit message:

```
# This is a combination of 3 commits.
# This is the 1st commit message:

Feat: Hello world

# This is the commit message #2:

WiP

# This is the commit message #3:

Feat: Print hello world 5 times

```

Remove commit message 2 because it does not contain any valid information

```
# This is a combination of 3 commits.
# This is the 1st commit message:

Feat: Hello world

# This is the commit message #3:

Feat: Print hello world 5 times
```

This way the commit history should only contain valid information and not temporary commits 

Before merging your branch you might want to squash some commits, for example commits that have no valid information should be squashed

rebase the last 3 commits
git rebase -i HEAD~3 

```
pick 402ca26 Feat: Hello world
pick c0a0a3a WiP
pick 3edcde3 Feat: Print hello world 5 times
```

change ```pick``` to ```squash``` or ```s``` of the commits you want to squash

```
pick 402ca26 Feat: Hello world
s c0a0a3a WiP
s 3edcde3 Feat: Print hello world 5 times
```

save the file. <br>
Commit message:

```
# This is a combination of 3 commits.
# This is the 1st commit message:

Feat: Hello world

# This is the commit message #2:

WiP

# This is the commit message #3:

Feat: Print hello world 5 times

```

Remove commit message 2 because it does not contain any valid information

```
# This is a combination of 3 commits.
# This is the 1st commit message:

Feat: Hello world

# This is the commit message #3:

Feat: Print hello world 5 times
```

This way the commit history should only contain valid information and not temporary commits 
