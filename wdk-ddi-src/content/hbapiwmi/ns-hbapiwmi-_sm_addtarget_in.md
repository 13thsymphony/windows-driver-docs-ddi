---
UID: NS.HBAPIWMI._SM_ADDTARGET_IN
title: _SM_AddTarget_IN
author: windows-driver-content
description: The SM_AddTarget_IN structure is used to provide input parameters to the SM_AddTarget WMI method.
old-location: storage\sm_addtarget_in.htm
old-project: storage
ms.assetid: 02bf5e91-bce0-4b8d-aec6-659ed1efd2b5
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _SM_AddTarget_IN, *PSM_AddTarget_IN, SM_AddTarget_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SM_AddTarget_IN
req.alt-loc: hbapiwmi.h
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

# _SM_AddTarget_IN structure



## -description
The SM_AddTarget_IN structure is used to provide input parameters to the SM_AddTarget WMI method.



## -syntax

````
typedef struct _SM_AddTarget_IN {
  UCHAR HbaPortWWN[8];
  UCHAR DiscoveredPortWWN[8];
  UCHAR DomainPortWWN[8];
  ULONG AllTargets;
} SM_AddTarget_IN, *PSM_AddTarget_IN;
````


## -struct-fields

### -field HbaPortWWN

The worldwide name (WWN) of the local port whose events the WMI client will receive.


### -field DiscoveredPortWWN

A worldwide name (WWN) that specifies the discovered target whose events the WMI client will receive.


### -field DomainPortWWN

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.


### -field AllTargets

The scope of the target events to report. If this member is zero, the WMI client will receive events that are associated with the port that is indicated by DiscoveredPortWWN. If this member is nonzero, the WMI client will receive events that are associated with all currently discovered targets as well as targets that are discovered in the future.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>