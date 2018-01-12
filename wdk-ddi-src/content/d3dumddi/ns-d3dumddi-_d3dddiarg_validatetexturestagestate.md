---
UID: NS:d3dumddi._D3DDDIARG_VALIDATETEXTURESTAGESTATE
title: _D3DDDIARG_VALIDATETEXTURESTAGESTATE
author: windows-driver-content
description: The D3DDDIARG_VALIDATETEXTURESTAGESTATE structure contains the number of passes in which the hardware can perform the blending operations that are specified in the current state.
old-location: display\d3dddiarg_validatetexturestagestate.htm
old-project: display
ms.assetid: 28d2efa5-a7bf-4b85-a0f3-a4bad705a874
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDIARG_VALIDATETEXTURESTAGESTATE, D3DDDIARG_VALIDATETEXTURESTAGESTATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_VALIDATETEXTURESTAGESTATE
req.alt-loc: d3dumddi.h
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
req.typenames: D3DDDIARG_VALIDATETEXTURESTAGESTATE
---

# _D3DDDIARG_VALIDATETEXTURESTAGESTATE structure



## -description
The D3DDDIARG_VALIDATETEXTURESTAGESTATE structure contains the number of passes in which the hardware can perform the blending operations that are specified in the current state.



## -syntax

````
typedef struct _D3DDDIARG_VALIDATETEXTURESTAGESTATE {
  UINT NumPasses;
} D3DDDIARG_VALIDATETEXTURESTAGESTATE;
````


## -struct-fields

### -field NumPasses

[in] The number of passes in which the hardware can perform the blending operations that are specified in the current state.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_validatedevice.md">ValidateDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_VALIDATETEXTURESTAGESTATE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

