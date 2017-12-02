---
UID: NE.rilapitypes.RILNOTIFICATIONFILTERMASK
title: RILNOTIFICATIONFILTERMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnotificationfiltermask_2.htm
old-project: netvista
ms.assetid: 00d083af-f2c1-4ad5-803a-5981ed70035f
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RIL_WritePhonebookEntry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILNOTIFICATIONFILTERMASK
req.alt-loc: rilapitypes.h
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
req.iface: 
req.product: Windows 10 or later.
---

# RILNOTIFICATIONFILTERMASK enumeration



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


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
<dl>

### -field RIL_NFS_SIGNALQUALITY

<dd></dd>

### -field RIL_NFS_REGSTATUS_RATKIND

<dd></dd>

### -field RIL_NFS_LOCATIONUPDATE

<dd></dd>

### -field RIL_NFS_ALL

<dd></dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>