---
UID: NS.IDDCX.IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT~R1
title: IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT
author: windows-driver-content
description: Gives information about the video output semantics for the OPM context that will be created.
old-location: display\idarg_in_opm_create_protected_output.htm
old-project: display
ms.assetid: c5727881-de35-4a61-bf54-0552d2de454b
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT,
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
req.alt-api: IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT
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

# IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT structure



## -description
Gives information about the video output semantics for the OPM  context that will be created.
             



## -syntax

````
typedef struct IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT {
  OPM_VIDEO_OUTPUT_SEMANTICS VideoOutputSemantics;
} IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT, *IDARG_IN_OPM_CREATE_PROTECTED_OUTPUT;
````


## -struct-fields

### -field VideoOutputSemantics


                     [in] Type of video output semantics used for this context.


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