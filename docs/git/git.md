## Git usage 

Do not develop on the ```main``` branch, the ```main``` branch should contain the latest (tested) version. 

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

# Commit message examples
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

# Squash 

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

# Branch naming 
When creating a new branch use a prefix for temporary development (these branches should be deleted once the work has been released).
<br>
Prefixes: <br>

* Features: feature/name_of_feature 
* bug fix: bug/name_of_bug 
* refactoring (if the refactor is a lot of work): refactor/reason
* development (e.g. building a complete new library): dev/name_of_development


# Clickup 
### Bug reports 
Reporting bugs should happen via Clickup, not directly via github (Clickup can create issues). 
Keeping the data in Clickup allows for a better overview of that status of bugs. 

Use the ```Bugs``` list to create a new ```Task``` in the ```Waiting for Triage``` section.
Steps: <br>

* Give the bug a proper name.
* Set the ```Priority```:
    * Low: No need to look at it for now.
    * Normal: Should be looked at within 2 weeks of reporting.
    * High: Should be looked at within 2 days of reporting.
    * Urgent: Requires being looked at within 2 hours of reporting.
* Set the ```Bug Severity```:
    * Trivial: Bug is not really causing any issues, more a 'nice to have'.
    * Minor: Bug is sometimes causing an issue.
    * Major: Bug is causing or could cause quite some issues. 
    * Critical: Bug is causing or could cause big issues or have impact on performance.
* Fill in ```Reported By```, for now keep this to the person writing the bug Task.
* Environment: Fill in which OS (Ubunt 20/24), Repository name and which branch 
* Steps to reproduce: If available describe how to recreate the bug, e.g. "If the X button was pressed while Y was happening, Z would crash".
* Expected outcome: If possible describe what should happen if the bug would be fixed, e.g. "Z would no longer crash, but an error message should popup on the screen"
* Tags: add possible tags that belong to this bug (no need to add the tag 'bug' because its a list of only bugs), e.g. 'ui', 'yaml' 
* Description: Write who reported the bug/issue, e.g. The operator from company ABC reported issue that when he pressed the X button, Z crashed.  
Write in details the information that describes the problem, possible suggestions and/or other information that you think is important to document. 
Does this happen often? Do you think this is related to something else? Was there a recent software update or other changes to the machine?
* Attachments: Add photos or log files that could help with understanding the issue. 
* Github: Create a new github issue (via Clickup), Set the issue title, select the correct Repository, and label as Bug. The description can be left empty because the information is in Clickup.
* Assignee: If possible assign it to the person(s) who have to work on the Bug, else leave empty 
* Report the bug in the Bugs channel such that every one is aware its created, if a specific person needs to work on it right away than contact that person directly. 

### Task tracking.
Currently there are 5 Steps for a Bug: Waiting for Triage, Investigating, In Progress, Testing / QA, Resolved. 

* Waiting for Triage: Task just created, waiting for somebody to start working on it.
* Investigating: The bug requires more information, more information, logs, etc.. 
* In Progress: The bug is being worked on.
* Testing / QA: There is a fix but still requires both testing and QA (Code Review) before it can be resolved. 
* Resolved: The bug has been fixed, tested and approved. 

In the future we can start adding Time Tracking and deadlines 

### Feature request

Use the ```Features``` list to create a new ```Task``` 
