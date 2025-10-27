---
content_type: page
description: This section provides supporting material for Lab 3.
learning_resource_types:
- Laboratory Assignments
ocw_type: CourseSection
parent_title: Labs
parent_type: CourseSection
parent_uid: 52bcf20c-777a-b4ef-31d4-6d96edf20ad1
title: Lab 3 Updates
uid: e87b2b25-33b9-6b81-4cf6-cc87068c405e
---

Fix the uMS Build
-----------------

### Getting uMS and FLTK to build

uMS is part of the MOOS software tree. There have been some problems in getting this to compile with the .build-moos.sh script.

Mac and Linux users both should do an "svn update" in the moos-ivp tree.

*   On Mac OS X, building uMS in the MOOS tree will require installing the FLTK package (sudo port install fltk-dev).
    
    It will also require augmenting your path:
    

```
bash users (add this to your .bashrc file): PATH=$PATH:~/moos-ivp/MOOS/MOOSBin/uMS.app/Contents/MacOS tcsh users: (add this to your .cshrc file) set path = ( $path ~/moos-ivp/MOOS/MOOSBin/uMS.app/Contents/MacOS )
```

*   In Linux:
    
    sudo apt-get install libfltk1.1-dev
    
    remove moos-ivp/MOOS/cmake\_modules/FindFLTK.cmake
    
    (or svn update - the above file has been removed from the tree).