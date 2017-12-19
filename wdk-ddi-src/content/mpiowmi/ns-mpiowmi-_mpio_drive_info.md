---
UID: NS.MPIOWMI._MPIO_DRIVE_INFO
title: _MPIO_DRIVE_INFO
author: windows-driver-content
description: The MPIO_DRIVE_INFO structure represents a multi-path disk in the system.
old-location: storage\mpio_drive_info.htm
old-project: storage
ms.assetid: 38d79fae-9701-4e92-bf73-4732e02c17ab
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _MPIO_DRIVE_INFO, MPIO_DRIVE_INFO, PMPIO_DRIVE_INFO, *PMPIO_DRIVE_INFO
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
req.alt-api: MPIO_DRIVE_INFO
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

# _MPIO_DRIVE_INFO structure



## -description
The MPIO_DRIVE_INFO structure represents a multi-path disk in the system.



## -syntax

````
typedef struct _MPIO_DRIVE_INFO {
  ULONG NumberPaths;
  WCHAR Name[63 + 1];
  WCHAR SerialNumber[63 + 1];
  WCHAR DsmName[63 + 1];
} MPIO_DRIVE_INFO, *PMPIO_DRIVE_INFO;
````


## -struct-fields

### -field NumberPaths

An unsigned 32-bitfield that represents the number of paths to the LUN.


### -field Name

A string field (of maximum length 63 characters) that returns the device name that was created by MPIO for the LUN.


### -field SerialNumber

A string field (of maximum length 63 characters) that returns the serial number that was created for the LUN by either the DSM or by MPIO itself.


### -field DsmName

A string field (of maximum length 63 characters) that returns the friendly name of the controlling DSM for the device.


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