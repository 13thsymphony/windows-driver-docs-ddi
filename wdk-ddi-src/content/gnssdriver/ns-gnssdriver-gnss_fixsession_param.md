---
UID : NS:gnssdriver.GNSS_FIXSESSION_PARAM
title : GNSS_FIXSESSION_PARAM
author : windows-driver-content
description : This structure defines the parameters used by the GNSS adapter to start a fix session.
old-location : sensors\gnss_fixsession_param.htm
old-project : sensors
ms.assetid : D51126FD-0448-487A-BD4E-170901E90B1E
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : sensors.gnss_fixsession_param, sensors.gnss_fixsesson_param, gnssdriver/GNSS_FIXSESSION_PARAM, GNSS_FIXSESSION_PARAM structure [Sensor Devices], GNSS_FIXSESSION_PARAM, PGNSS_FIXSESSION_PARAM structure pointer [Sensor Devices], PGNSS_FIXSESSION_PARAM, gnssdriver/PGNSS_FIXSESSION_PARAM, *PGNSS_FIXSESSION_PARAM
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : gnssdriver.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PGNSS_FIXSESSION_PARAM, GNSS_FIXSESSION_PARAM"
---

# GNSS_FIXSESSION_PARAM structure
This structure defines the parameters used by the GNSS adapter to start a fix session.

## Syntax
````
typedef struct {
  ULONG               Size;
  ULONG               Version;
  ULONG               FixSessionID;
  GNSS_FIXSESSIONTYPE SessionType;
  ULONG               HorizontalAccuracy;
  ULONG               HorizontalConfidence;
  ULONG               Reserved[9];
  ULONG               FixLevelOfDetails;
  union {
    GNSS_SINGLESHOT_PARAM         SingleShotParam;
    GNSS_DISTANCETRACKING_PARAM   DistanceParam;
    GNSS_CONTINUOUSTRACKING_PARAM ContinuousParam;
    GNSS_LKGFIX_PARAM             LkgFixParam;
  };
  BYTE                Unused[512];
} GNSS_FIXSESSION_PARAM, *PGNSS_FIXSESSION_PARAM;
````

## Members


`FixLevelOfDetails`

Indicates the level of detail needed when the GNSS driver returns the fix information.

The GNSS driver may choose to override this input.

This flag is OR-ed with the bit-values defined in GNSS_FIXDETAIL_* mask.

`FixSessionID`

This is a unique identifier for a particular fix session.

 The GNSS adapter generates this number in a monotonically increasing order whenever a new fix session is requested. The number wraps around to zero. Given the lifetime of an active session and the number of possible parallel sessions even with multi-session support, the wrap-around is acceptable in this use case.

The GNSS driver must associate all fix related data to the original fix session by using the FixSessionID field. If the GNSS driver does not support multiple fix sessions, it may use the session ID of the last fix session request.

`HorizontalAccuracy`

The horizontal accuracy of the fix requested is only advisory information for the GNSS driver that can be used in an implementation-specific manner for making appropriate tradeoffs internally to satisfy the request.

A value of 0 indicates no particular accuracy is mandated by the GNSS adapter.

`HorizontalConfidence`

The horizontal confidence is the circular confidence requested for this fix.

The platform expects fixes with a 95% confidence. The GNSS driver should honor this confidence value when it returns the fix and accuracy from the GNSS engine.

`Reserved`



`SessionType`

Identifies the type or recurrence type of this fix session.

`Size`

Structure size.

`Unused`



`Version`

Version number.

## Remarks
The fix session parameters are different for different types of sessions. This structure contains a common set of parameters applicable for all fix sessions, followed by an overloaded structure (union) for each fix session type. The GNSS driver must use the appropriate structure from the union depending on the session type.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | gnssdriver.h |