---
UID: NS.IDDCX.IDARG_OUT_QUERYTARGETMODES
title: IDARG_OUT_QUERYTARGETMODES
author: windows-driver-content
description: Gives information about the number of target modes provided by the OS.
old-location: display\idarg_out_querytargetmodes.htm
old-project: display
ms.assetid: 427af891-1fb7-4042-89bc-a40191ec5a31
ms.author: windowsdriverdev
ms.date: 12/6/2017
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
req.irql: 
---

# IDARG_OUT_QUERYTARGETMODES structure



## -description

                 Gives information about the number of target modes provided by the OS.


## -syntax

````
typedef struct IDARG_OUT_QUERYTARGETMODES {
  UINT TargetModeBufferOutputCount;
} IDARG_OUT_QUERYTARGETMODES, *IDARG_OUT_QUERYTARGETMODES;
````


## -struct-fields

### -field TargetModeBufferOutputCount


                       [out] If the OS provides the number of target modes, the driver sets this to that value. 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>