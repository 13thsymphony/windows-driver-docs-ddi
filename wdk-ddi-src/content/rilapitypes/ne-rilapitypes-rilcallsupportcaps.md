---
UID: NE.rilapitypes.RILCALLSUPPORTCAPS
title: RILCALLSUPPORTCAPS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallsupportcaps_2.htm
old-project: netvista
ms.assetid: f51ab865-8862-4ed2-830e-ecbef4c9c74e
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILCALLSUPPORTCAPS, RILCALLSUPPORTCAPS
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
req.alt-api: RILCALLSUPPORTCAPS
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
req.product: Windows 10 or later.
---

# RILCALLSUPPORTCAPS enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax

````
typedef enum _RILCALLSUPPORTCAPS { 
  RIL_CAPS_CALLSUPPORT_CD,
  RIL_CAPS_CALLSUPPORT_CNAP,
  RIL_CAPS_CALLSUPPORT_CUG,
  RIL_CAPS_CALLSUPPORT_EMLPP,
  RIL_CAPS_CALLSUPPORT_FM,
  RIL_CAPS_CALLSUPPORT_MSP,
  RIL_CAPS_CALLSUPPORT_USSD_PHASE2,
  RIL_CAPS_CALLSUPPORT_USS,
  RIL_CAPS_CALLSUPPORT_ALL
} RILCALLSUPPORTCAPS;
````


## -enum-fields

### -field RIL_CAPS_CALLSUPPORT_CD


### -field RIL_CAPS_CALLSUPPORT_CNAP


### -field RIL_CAPS_CALLSUPPORT_CUG


### -field RIL_CAPS_CALLSUPPORT_EMLPP


### -field RIL_CAPS_CALLSUPPORT_FM


### -field RIL_CAPS_CALLSUPPORT_MSP


### -field RIL_CAPS_CALLSUPPORT_USSD_PHASE2


### -field RIL_CAPS_CALLSUPPORT_USS


### -field RIL_CAPS_CALLSUPPORT_ALL


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>