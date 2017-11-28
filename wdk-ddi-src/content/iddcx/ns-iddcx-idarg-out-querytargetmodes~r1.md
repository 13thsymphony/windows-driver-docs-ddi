---
UID: NS.iddcx.IDARG_OUT_QUERYTARGETMODES~r1
title: IDARG_OUT_QUERYTARGETMODES
author: windows-driver-content
description: Gives information about the number of target modes provided by the OS.
old-location: display\idarg_out_querytargetmodes.htm
old-project: display
ms.assetid: 427af891-1fb7-4042-89bc-a40191ec5a31
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: IDARG_OUT_QUERYTARGETMODES,
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
req.alt-api: IDARG_OUT_QUERYTARGETMODES
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

# IDARG_OUT_QUERYTARGETMODES structure



## -description
<p>
                 Gives information about the number of target modes provided by the OS.</p>


## -syntax

````
typedef struct IDARG_OUT_QUERYTARGETMODES {
  UINT TargetModeBufferOutputCount;
} IDARG_OUT_QUERYTARGETMODES, *IDARG_OUT_QUERYTARGETMODES;
````


## -struct-fields
<dl>

### -field <b>TargetModeBufferOutputCount</b>

<dd>
<p>
                       [out] If the OS provides the number of target modes, the driver sets this to that value. </p>
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