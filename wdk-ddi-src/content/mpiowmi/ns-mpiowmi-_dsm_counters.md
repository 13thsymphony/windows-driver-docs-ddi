---
UID: NS:mpiowmi._DSM_COUNTERS
title: "_DSM_COUNTERS"
author: windows-driver-content
description: The DSM_COUNTERS structure holds the various timer counters that are applicable to all LUNs that are controlled by the DSM.
old-location: storage\dsm_counters.htm
old-project: storage
ms.assetid: 3202aec4-d95e-4162-86a1-17595ed2a5b5
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.dsm_counters, mpiowmi/DSM_COUNTERS, DSM_COUNTERS, *PDSM_COUNTERS, PDSM_COUNTERS, PDSM_COUNTERS structure pointer [Storage Devices], mpiowmi/PDSM_COUNTERS, DSM_COUNTERS structure [Storage Devices], structs-scsibus_bfb9b1ff-6274-47b9-b817-254428b02f17.xml, _DSM_COUNTERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	mpiowmi.h
apiname:
-	DSM_COUNTERS
product: Windows
targetos: Windows
req.typenames: DSM_COUNTERS, *PDSM_COUNTERS
---

# _DSM_COUNTERS structure
The DSM_COUNTERS structure holds the various timer counters that are applicable to all LUNs that are controlled by the DSM.

## Syntax
````
typedef struct _DSM_COUNTERS {
  ULONG     PathVerifyEnabled;
  ULONG     PathVerificationPeriod;
  ULONG     PDORemovePeriod;
  ULONG     RetryCount;
  ULONG     RetryInterval;
  ULONG     Reserved32;
  ULONGLONG Reserved64;
} DSM_COUNTERS, *PDSM_COUNTERS;
````

## Members


`PathVerificationPeriod`

An unsigned 32-bitfield that is used to indicate the periodicity (in seconds) with which MPIO has been requested to perform path verification. This field is only honored if <i>PathVerifyEnabled</i> is <b>TRUE</b>.

`PathVerifyEnabled`

An unsigned 32-bitfield that is used as a flag. This field indicates if path verification must be performed by MPIO periodically on all paths that expose devices that are controlled by this particular DSM.

`PDORemovePeriod`

An unsigned 32-bitfield that controls the amount of time (in seconds) that the pseudo-LUN will continue to remain in system memory, even after losing all its path information.

`Reserved32`

Should be zero.

`Reserved64`

Should be zero.

`RetryCount`

An unsigned 32-bitfield that specifies the number of times a failed I/O will be retried.

`RetryInterval`

An unsigned 32-bitfield that specifies the interval of time (in seconds) after which a failed request is retried.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | mpiowmi.h (include Mpiowmi.h) |