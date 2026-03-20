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

# CMake 

Cmake part for possibilty to create .deb file
```
set(CPACK_GENERATOR "DEB")
set(CPACK_DEBIAN_PACKAGE_MAINTAINER "CobotX")
include(CPack)
set(CPACK_PACKAGE_NAME ${CMAKE_PROJECT_NAME})
set(CPACK_PACKAGE_VERSION ${PROJECT_VERSION})

```

To create the .deb file:
```
cmake --build . --target package
```

# Release 

When the dev branch has been approved a release can be generated. 
Generate a tag using 
```
git tag -a v1.2.3
```
and push the tag 
```
git push origin v1.2.3
```

On the github page of the repository create a new release, using the just created tag, write the release notes and upload the created .deb file. 

# Dependency 

If your library depends on another library you have to update the Config.cmake.in file located in the cmake directory. 
```
include(CMakeFindDependencyMacro)
find_dependency(library_name x.y.z REQUIRED)
```
The library_name and version (x.y.z) has to be the same as the find_package variables

# Library manager 

The [library_manager](https://github.com/CobotX-Zwolle/library_manager) can be used to download all .deb files from the repositories, 
its important to keep this file up-to-date with the latest versions. 
Update the libraries.json file with either the new repository name and/or add the new version to it. 
Download the .deb files
```
python3 update_libraries.py
```

* TODO: this requires ```gh``` to be installed and configured (needs some instructions).
* TODO: see if this can be automated to parse all available tags and download the .deb files from them without having to add the versions manually.

