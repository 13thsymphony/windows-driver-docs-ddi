---
UID: NS:storport._STARTIO_PERFORMANCE_PARAMETERS
title: "_STARTIO_PERFORMANCE_PARAMETERS"
author: windows-driver-content
description: The STARTIO_PERFORMANCE_PARAMETERS structure describes the performance parameters that are returned to the miniport driver by the StorPortGetStartIoPerfParams routine.
old-location: storage\startio_performance_parameters.htm
old-project: storage
ms.assetid: 984a8584-ebdd-4e93-868b-1537a3615c1b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSTARTIO_PERFORMANCE_PARAMETERS, PSTARTIO_PERFORMANCE_PARAMETERS, PSTARTIO_PERFORMANCE_PARAMETERS structure pointer [Storage Devices], STARTIO_PERFORMANCE_PARAMETERS, STARTIO_PERFORMANCE_PARAMETERS structure [Storage Devices], _STARTIO_PERFORMANCE_PARAMETERS, storage.startio_performance_parameters, storport/PSTARTIO_PERFORMANCE_PARAMETERS, storport/STARTIO_PERFORMANCE_PARAMETERS, structs-storport_6f0f3ae8-51e3-4c3e-91e1-4603b04b6f08.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	STARTIO_PERFORMANCE_PARAMETERS
product: Windows
targetos: Windows
req.typenames: STARTIO_PERFORMANCE_PARAMETERS, *PSTARTIO_PERFORMANCE_PARAMETERS
req.product: Windows 10 or later.
---

# _STARTIO_PERFORMANCE_PARAMETERS structure
The <b>STARTIO_PERFORMANCE_PARAMETERS</b> structure describes the performance parameters that are returned to the miniport driver by the <a href="..\storport\nf-storport-storportgetstartioperfparams.md">StorPortGetStartIoPerfParams</a> routine.

## Syntax
````
typedef struct _STARTIO_PERFORMANCE_PARAMETERS {
  ULONG Version;
  ULONG Size;
  ULONG MessageNumber;
  ULONG ChannelNumber;
} STARTIO_PERFORMANCE_PARAMETERS, *PSTARTIO_PERFORMANCE_PARAMETERS;
````

## Members


`Version`

The version number of the structure. This member is valid starting with Windows 8.

`Size`

The size of the structure.

`MessageNumber`

The offset in the device's MSI-X table for the optimal MSI-X message with which to interrupt. If the device does not support MSI-X messages, this member will be zero.

`ChannelNumber`

Denotes the concurrent channel in which Storport is passing the I/O. If the miniport driver did not set up concurrent channels, this member will be zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | storport.h (include Storport.h) |

## See Also

<a href="..\storport\nf-storport-storportgetstartioperfparams.md">StorPortGetStartIoPerfParams</a>