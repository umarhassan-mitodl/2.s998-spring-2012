---
content_type: page
description: This section provides supporting material for Lab 6.
learning_resource_types:
- Laboratory Assignments
ocw_type: CourseSection
parent_title: Labs
parent_type: CourseSection
parent_uid: 52bcf20c-777a-b4ef-31d4-6d96edf20ad1
title: Lab 6 Updates
uid: 59c5b6bb-44a9-c4b9-974d-a4b1f5553132
---

Depth Configurations
--------------------

In the Alpha example, the moos-ivp version of a Hello World program, the vehicle is a simulated surface craft. To simulated a UUV, a few modifications are required of three MOOS applications, including the helm. Once this is done, behaviors reasoning about depth may be used in the helm.

### Modifications to the uSimMarine MOOS module:

More information on the uSimMarine simulator and configuration options can be found in the {{% resource_link "30af7283-95e1-4ead-bd90-a03bb8db4c23" "moos-ivp autonomy utilities documentation (PDF - 29.2MB)" %}}.

```
     BUOYANCY_RATE        = 0.025     MAX_DEPTH_RATE       = 5     MAX_DEPTH_RATE_SPEED = 2.0     DEFAULT_WATER_DEPTH  = 400 
```

### Modifications to the pMarinePID MOOS module:

More information on the uSimMarine simulator and configuration options can be found in the utilities {{% resource_link "30af7283-95e1-4ead-bd90-a03bb8db4c23" "moos-ivp autonomy documentation (PDF - 29.2MB)" %}}.

```
     DEPTH_CONTROL = true        //Pitch PID controller     PITCH_PID_KP                   = 1.5     PITCH_PID_KD                   = 1.0     PITCH_PID_KI                   = 0     PITCH_PID_INTEGRAL_LIMIT       = 0        //ZPID controller     Z_TO_PITCH_PID_KP              = 0.12     Z_TO_PITCH_PID_KD              = 0     Z_TO_PITCH_PID_KI              = 0.004     Z_TO_PITCH_PID_INTEGRAL_LIMIT  = 0.05     MAXPITCH     = 15     MAXELEVATOR  = 13 
```

### Modifications to the pHelmIvP MOOS module:

More information on configuring the IvPHelm decision domain may be found on p. 47 in the {{% resource_link "30af7283-95e1-4ead-bd90-a03bb8db4c23" "helm documentation (PDF - 29.2MB)" %}}.

```
Domain     = depth:0:100:101
```

### Modifications to the pNodeReporter MOOS module:

The modification below to pNodeReporter is mostly cosmetic. It changes the vehicle type to "UUV" so you see a UUV icon in your simulator diving, rather than a kayak. More information on pNodeReporter and configuration options can be found in the {{% resource_link "30af7283-95e1-4ead-bd90-a03bb8db4c23" "moos-ivp autonomy utilities documentation (PDF - 29.2MB)" %}}.

```
VESSEL_TYPE   = UUV
```