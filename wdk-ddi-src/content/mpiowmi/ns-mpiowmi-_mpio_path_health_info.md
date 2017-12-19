---
UID: NS.MPIOWMI._MPIO_PATH_HEALTH_INFO
title: _MPIO_PATH_HEALTH_INFO
author: windows-driver-content
description: The MPIO_PATH_HEALTH_INFO structure is used to query the available health information for every path that is exposed to the system.
old-location: storage\mpio_path_health_info.htm
old-project: storage
ms.assetid: efb49852-3c0a-4dab-9d50-c103ba4a136b
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _MPIO_PATH_HEALTH_INFO, MPIO_PATH_HEALTH_INFO, *PMPIO_PATH_HEALTH_INFO, PMPIO_PATH_HEALTH_INFO
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
req.alt-api: MPIO_PATH_HEALTH_INFO
req.alt-loc: mpiowmi.h
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
---

# _MPIO_PATH_HEALTH_INFO structure



## -description
The MPIO_PATH_HEALTH_INFO structure is used to query the available health information for every path that is exposed to the system.



## -syntax

````
typedef struct _MPIO_PATH_HEALTH_INFO {
  ULONG                  NumberPathPackets;
  ULONG                  Reserved;
  MPIO_PATH_HEALTH_CLASS PathHealthPackets[1];
} MPIO_PATH_HEALTH_INFO, *PMPIO_PATH_HEALTH_INFO;
````


## -struct-fields

### -field NumberPathPackets

An unsigned 32-bitfield that returns the number of health packets available that correspond to the number of available paths under MPIO control.


### -field Reserved

Should be zero.


### -field PathHealthPackets

A field that contains an array with health information about all the available paths under MPIO control. The number of elements of the array is given by NumberPathPackets and each element of the array is an instance of the MPIO_PATH_HEALTH_CLASS structure.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Mpiowmi.h (include Mpiowmi.h)</dt>
</dl>
</td>
</tr>
</table>