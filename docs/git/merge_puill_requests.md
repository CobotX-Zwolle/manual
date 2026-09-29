* No "large" (project) Pull Request
    * Identify desirable changes (features, bug fixes) from the project -> make individual commits for each.
* Create 1 dev branch with multiple features and bug fixes -> update version appropriately 
    * feature / bug brnaches for testing
    * test dev branch to check for compatbility
    * make sure main is merged into the dev branch before performing testing and performing the pull-request.
* Check each commit / merge on what is changed 
    * git merge is known to undo some changes so check ALL changes not just the merge conflicts
    * Git diff show the difference in commits, which are the code CHANGES, it does not show the actual difference between the files
        * git diff can show a change that has already happened on both branches for example, making it unclear what exactly will happen when merging
