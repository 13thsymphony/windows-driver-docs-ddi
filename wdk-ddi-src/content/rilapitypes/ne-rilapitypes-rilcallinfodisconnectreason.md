---
UID: NE.rilapitypes.RILCALLINFODISCONNECTREASON
title: RILCALLINFODISCONNECTREASON
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfodisconnectreason_2.htm
old-project: netvista
ms.assetid: b0cc8ecb-fa13-414a-b08a-de0d60724f25
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
req.alt-api: RILCALLINFODISCONNECTREASON
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

# RILCALLINFODISCONNECTREASON enumeration



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef enum _RILCALLINFODISCONNECTREASON { 
  RIL_DISCREASON_BUSY,
  RIL_DISCREASON_NETWORKERROR,
  RIL_DISCREASON_RADIOFADE,
  RIL_DISCREASON_CONGESTION,
  RIL_DISCREASON_EMERGENCYONLY,
  RIL_DISCREASON_NOSERVICE,
  RIL_DISCREASON_OTHEREXECUTORBUSY,
  RIL_DISCREASON_EMERGENCYFAILOVER,
  RIL_DISCREASON_HANDOVER_MERGE,
  RIL_DISCREASON_MAX
} RILCALLINFODISCONNECTREASON;
````


## -enum-fields
<dl>

### -field RIL_DISCREASON_BUSY

<dd></dd>

### -field RIL_DISCREASON_NETWORKERROR

<dd></dd>

### -field RIL_DISCREASON_RADIOFADE

<dd></dd>

### -field RIL_DISCREASON_CONGESTION

<dd></dd>

### -field RIL_DISCREASON_EMERGENCYONLY

<dd></dd>

### -field RIL_DISCREASON_NOSERVICE

<dd></dd>

### -field RIL_DISCREASON_OTHEREXECUTORBUSY

<dd></dd>

### -field RIL_DISCREASON_EMERGENCYFAILOVER

<dd></dd>

### -field RIL_DISCREASON_HANDOVER_MERGE

<dd></dd>

### -field RIL_DISCREASON_MAX

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