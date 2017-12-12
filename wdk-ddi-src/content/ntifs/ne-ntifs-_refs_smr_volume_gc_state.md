---
UID: NE.ntifs._REFS_SMR_VOLUME_GC_STATE
title: _REFS_SMR_VOLUME_GC_STATE
author: windows-driver-content
description: The REFS_SMR_VOLUME_GC_STATE enum specifies the garbage collection's current state.
old-location: ifsk\refs_smr_volume_gc_state.htm
old-project: ifsk
ms.assetid: 9E75F65A-6E9C-485F-9437-30CB01A5F317
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _REFS_SMR_VOLUME_GC_STATE, REFS_SMR_VOLUME_GC_STATE, *PREFS_SMR_VOLUME_GC_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: REFS_SMR_VOLUME_GC_STATE
req.alt-loc: Ntifs.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _REFS_SMR_VOLUME_GC_STATE enumeration



## -description
The <b>REFS_SMR_VOLUME_GC_STATE</b> enum specifies the garbage collection's current state.



## -syntax

````
typedef enum _REFS_SMR_VOLUME_GC_STATE { 
  SmrGcStateInactive         = 0,
  SmrGcStatePaused           = 1,
  SmrGcStateActive           = 2,
  SmrGcStateActiveFullSpeed  = 3
} REFS_SMR_VOLUME_GC_STATE, *PREFS_SMR_VOLUME_GC_STATE;
````


## -enum-fields

### -field SmrGcStateInactive

Specifies the garbage collection is inactive.


### -field SmrGcStatePaused

 Specifies the garbage collection has been paused.


### -field SmrGcStateActive

Specifies the garbage collection is running.


### -field SmrGcStateActiveFullSpeed

Specifies the garbage collection is running at full speed.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 10, version 1709.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>