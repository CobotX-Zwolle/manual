## Version 

Always use Major.Minor.Patch versions, e.g v1.2.3

When developing a new library start with version v0.1.0, once the version is ready to be released it can be upgraded to v1.0.0.

# Updating new versions 

* Small updates, like refactors, bug fixes should bump the Patch version by 1. 
* New features that ```not``` break backwards compatibility should bump the Minor version by 1. 
* New features and/or changes to current features that break compatibility should bump the Major version by 1.

If a Minor gets updated it should reset the Patch version to 0. 
If a Major gets updated it should reset Minor and Patch to 0. 


# Development 

When developing a new version do not use the version as branch name (e.g. v1.0.1), because the version number will be used for a 'tag', which can be used to release the version.  
<br>
When creating a new branch use a prefix for temporary development (these branches should be deleted once the work has been released).
<br>
Prefixes: <br>

* Features: feature/name_of_feature 
* bug fix: bug/name_of_bug 
* refactoring (if the refactor is a lot of work): refactor/reason

Once you are done with the work create a new branch dev/vx.y.z depending on which version you are updating, this branch can contain multiple new features or multiple bug fixes. 
This branch will require a Pull Request to the main branch, once the dev/vx.y.z has been approved a tag has to be created and a release has to be made. 

TODO: Instructions on release notes


