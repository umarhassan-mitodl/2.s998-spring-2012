---
content_type: page
description: This page describes how to scope the MOOSDB. Scoping refers to the idea
  of having a view into the current state (or even recent history) of the MOOSDB.
learning_resource_types: []
ocw_type: CourseSection
parent_title: MOOS Basics
parent_type: CourseSection
parent_uid: dab1dc4f-1da2-1ac2-f601-43a182449e27
title: Scoping the MOOSDB
uid: 6129bdf2-4f42-a34b-e5e2-f69d085a02ce
---

This page describes how to scope the MOOSDB. Scoping refers to the idea of having a view into the current state (or even recent history) of the MOOSDB. There are multiple tools for scoping the DB, each providing conveniences of one kind or another to the user. Here we describe the uXMS and uMS tools, the two favorites of our own lab.

Where to get more information:

*   uXMS: From the MOOS-IvP Autonomy Tools Users Manual (find the most recent version of this document {{% resource_link "d9da38d5-a0e8-49c6-970b-808d0baf80d4" "here" %}}).
*   uMS: {{% resource_link "57af08ab-60f3-4742-bb85-400929a64add" "The MOOS Documents page" %}}.

Scoping the MOOSDB with uXMS
----------------------------

uXMS is a terminal based scope. It may be launched from the command-line, passing it a .moos file. Several command-line options are available; a full list may be seen by passing it the—**help** command-line option. If simply a MOOSDB is running, launching uXMS may look like:

```

$ uXMS moosdb_alpha.moos --all --show=time
  ****************************************************
  *                                                  *
  *       This is MOOS Client                        *
  *       c. P Newman 2001                           *
  *                                                  *
  ****************************************************
		
  ---------------MOOS CONNECT-----------------------
    contacting a MOOS server localhost:9000 -  try 00001 
    Contact Made
    Handshaking as "uXMS_418"
    Handshaking Complete
    Invoking User OnConnect() callback...ok
  --------------------------------------------------

  uXMS_418 is Running:
  	 AppTick   @ 5.0 Hz
  	 CommsTick @ 10 Hz

   VarName                (S) (T)ime       (C) VarValue (MODE = SCOPE:EVENTS)
   ----------------       --- ----------   ---  ----------- (2)
   DB_CLIENTS                  19.99            "uXMS_318,DBWebServer,"
   DB_TIME                     19.99            1329084452.15727
   DB_UPTIME                   19.99            20.0471
   -- displaying all variables --
```

The three variables shown are all published by the MOOSDB. The user may choose whether or not to show the variable (S)ource, (T)ime of post, or (C)ommunity from where the post was made. key feature of uXMS vs. uMS is the ability to specify on the command-line exactly which subset of variables to scope, possibly with color-coding. This is helpful when there are hundreds of variables in the DB.

Scoping the MOOSDB with uMS
---------------------------

uMS is a GUI-based tool for scoping the MOOSDB. It may be invoked from the command-line similarly by passing it a .moos file describing where a MOOSDB is running:

```
$ uMS moosdb_alpha.moos
```

Upon launch, and clicking the "Connect" button, you should see a new window.