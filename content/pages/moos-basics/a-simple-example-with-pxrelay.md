---
content_type: page
description: This page describes pXRelay usage and gives a simple example with pXRelay.
learning_resource_types: []
ocw_type: CourseSection
parent_title: MOOS Basics
parent_type: CourseSection
parent_uid: dab1dc4f-1da2-1ac2-f601-43a182449e27
title: A Simple Example with pXRelay
uid: 9aeae296-987a-a81f-109a-2cc49293b92a
---

A Simple Example with pXRelay
-----------------------------

pXRelay is a simple MOOS app designed solely to illustrate basic functions of a MOOS app. It registers for a single variable, and upon receipt mail for that variable, it publishes another variable incremented by 1. It provides a framework for illustrating few other introductory topics.

Where to get more information:

*   Type pXRelay—example on the command line.
*   [An Overview of MOOS-IvP and a Users Guide to the IvP Helm (Section 3.8) (PDF)](http://oceanai.mit.edu/moos-ivp-pdf/moosivp-helm.pdf)

Basic pXRelay Usage
-------------------

pXRelay is configured with its own block in the MOOS configuration file. It is configured with (a) an _incoming variable_, the variable it will register for incoming mail, and (b) an _outgoing variable_, a variable it will post an incremented integer each time it receives mail on the incoming variable. The basic form is:

```
 ProcessConfig = pXRelay
 {
   OUTGOING_VAR = 
   INCOMING_VAR = 
 } 
```

A Simple Example with pXRelay
-----------------------------

The below mission file contains a configuration for two instances of the pXRelay application. All MOOS apps must have a unique name to connect to the MOOSDB, so we launch them with an alias with pAntler using the **~pXRelay\_PEARS** alias for example. The two apps each register for what the other produces, and each produces what the other registers for.

```
 // (wget http://oceanai.mit.edu/2.S998/examples/xrelay.moos)
 ServerHost = localhost
 ServerPort = 9000
 Community  = alpha

  ProcessConfig = ANTLER
  {
   MSBetweenLaunches = 200

   Run = MOOSDB       @ NewConsole = false
   Run = pXRelay      @ NewConsole = false ~pXRelay_PEARS
   Run = pXRelay      @ NewConsole = false ~pXRelay_APPLES
  }

  ProcessConfig = pXRelay_APPLES
  {
   AppTick       = 10
   CommsTick     = 10
   INCOMING_VAR  = APPLES
   OUTGOING_VAR  = PEARS
  }

  ProcessConfig = pXRelay_PEARS
  {
   AppTick       = 10
   CommsTick     = 10
   INCOMING_VAR  = PEARS
   OUTGOING_VAR  = APPLES
  } 
```

Upon launch, the two pXRelay apps are in a stalemate, each waiting for the other to make the first posting. We can break this stalemate with uPokeDB:

```
 $ uPokeDB xrelay.moos PEARS=1 
```

This should get things going. Now it would be good to see it all running by launching a scope:

```
 $ uXMS xrelay.moos --all --show=time 
```