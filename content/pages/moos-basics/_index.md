---
content_type: page
description: This section contains links to pages on introductory MOOS topics designed
  for the absolutely new MOOS user.
learning_resource_types: []
ocw_type: CourseSection
title: MOOS Basics
uid: dab1dc4f-1da2-1ac2-f601-43a182449e27
---

Getting Started with MOOS Basics
--------------------------------

These pages contain a handful of introductory MOOS topics designed for the absolutely new MOOS user.

*   {{% resource_link 72c27940-a2e0-2452-abf2-720d0762289d "Launching the MOOSDB" %}}:
    
    The MOOSDB is the heart of MOOS. This page describes how it may be simply launched from the command line. Later we'll see that typically the MOOSDB is launched as part of a group MOOS apps with the pAntler tool. But this a good page to start for someone who has never before launched the MOOSDB.
    
*   {{% resource_link 6129bdf2-4f42-a34b-e5e2-f69d085a02ce "Scoping the MOOSDB" %}}:
    
    This page describes how to scope the MOOSDB. Scoping refers to the idea of having a view into the current state (or even recent history) of the MOOSDB. This page describes the uXMS and uMS tools, among the several ways to scope the MOOSDB.
    
*   {{% resource_link 5822be6d-78f0-0532-ffe7-b39618190670 "Poking the MOOSDB" %}}:
    
    This page describes how to poke the MOOSDB. Poking refers to the idea of publishing a variable-value pair to the MOOSDB. Poking implies a publication that perhaps was not planned, or outside the normal mode of business. It is often very useful for debugging. Here we describe the uPokeDB tool.
    
*   {{% resource_link f084e04e-e786-d502-fe78-239c1e543b2c "Launching a Mission with pAntler" %}}:
    
    This page describes how to launch a set of MOOS applications with pAntler. In theory, a set of N applications may be launched from N terminal windows, but this is cumbersome in practice. The pAntler tool allows a block to be declared in a mission file (.moos file) listing all the apps to be launched in one go.
    
*   {{% resource_link 8ffb37cc-bdb1-028a-cf64-4b911bacbd7d "Scripted Pokes to the MOOSDB" %}}:
    
    This page describes MOOS scripting: configuring a set of pre-arranged pokes, at pre-arranged times to the MOOSDB. This may be useful for a number of reasons besides debugging. The primary tool described here is the uTimerScript MOOS application.
    
*   {{% resource_link 9aeae296-987a-a81f-109a-2cc49293b92a "A Simple Example with pXRelay" %}}:
    
    pXRelay is a simple MOOS app designed solely to illustrate basic functions of a MOOS app. It registers for a single variable, and upon receipt mail for that variable, it publishes another variable incremented by 1. It provides a framework for illustrating few other introductory topics.