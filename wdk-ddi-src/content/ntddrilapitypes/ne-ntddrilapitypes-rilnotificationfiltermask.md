---
UID: NE.ntddrilapitypes.RILNOTIFICATIONFILTERMASK
title: RILNOTIFICATIONFILTERMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnotificationfiltermask.htm
old-project: netvista
ms.assetid: 5dc72657-00ae-4fde-b9a7-a63616d934c0
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILNOTIFICATIONFILTERMASK, RILNOTIFICATIONFILTERMASK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILNOTIFICATIONFILTERMASK
req.alt-loc: ntddrilapitypes.h
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

# RILNOTIFICATIONFILTERMASK enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax

````
typedef enum _RILNOTIFICATIONFILTERMASK { 
  RIL_NFS_SIGNALQUALITY,
  RIL_NFS_REGSTATUS_RATKIND,
  RIL_NFS_LOCATIONUPDATE,
  RIL_NFS_ALL
} RILNOTIFICATIONFILTERMASK;
````


## -enum-fields

### -field RIL_NFS_SIGNALQUALITY


### -field RIL_NFS_REGSTATUS_RATKIND


### -field RIL_NFS_LOCATIONUPDATE


### -field RIL_NFS_ALL


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>