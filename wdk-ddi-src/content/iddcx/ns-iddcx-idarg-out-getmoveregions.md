---
UID: NS.iddcx.IDARG_OUT_GETMOVEREGIONS
title: IDARG_OUT_GETMOVEREGIONS
author: windows-driver-content
description: Gives information about move regions that were handled by the OS.
old-location: display\idarg_out_getmoveregions.htm
old-project: display
ms.assetid: b95b2da7-8078-4e71-91db-a1b399bc44a2
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: IDARG_OUT_GETMOVEREGIONS,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDARG_OUT_GETMOVEREGIONS
req.alt-loc: iddcx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _Must_inspect_result_
req.iface: 
---

# IDARG_OUT_GETMOVEREGIONS structure



## -description
<p>Gives information about move regions that were handled by the OS.</p>


## -syntax

````
typedef struct IDARG_OUT_GETMOVEREGIONS {
  UINT MoveRegionOutCount;
} IDARG_OUT_GETMOVEREGIONS, *IDARG_OUT_GETMOVEREGIONS;
````


## -struct-fields
<dl>

### -field <b>MoveRegionOutCount</b>

<dd>
<p>
                     [out] Number of move regions the OS copied into the <b>pMoveRegions</b> array.</p>
</dd>
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
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>