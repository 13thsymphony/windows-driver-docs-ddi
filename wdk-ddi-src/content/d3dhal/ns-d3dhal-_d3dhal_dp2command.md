---
UID: NS:d3dhal._D3DHAL_DP2COMMAND
title: _D3DHAL_DP2COMMAND
author: windows-driver-content
description: One or more D3DHAL_DP2COMMAND structures are parsed from the command buffer by the D3dDrawPrimitives2 callback, which uses the information it receives to draw one or more primitives.
old-location: display\d3dhal_dp2command.htm
old-project: display
ms.assetid: 3fa32e5c-32d5-4e26-82b5-45dbf5389f2b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DHAL_DP2COMMAND, *LPD3DHAL_DP2COMMAND, D3DHAL_DP2COMMAND
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DHAL_DP2COMMAND
req.alt-loc: d3dhal.h
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
req.typenames: *LPD3DHAL_DP2COMMAND, D3DHAL_DP2COMMAND
---

# _D3DHAL_DP2COMMAND structure



## -description
One or more D3DHAL_DP2COMMAND structures are parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback, which uses the information it receives to draw one or more primitives. Each structure specifies either a primitive to draw or a state change to process.



## -syntax

````
typedef struct _D3DHAL_DP2COMMAND {
  BYTE  bCommand;
  BYTE  bReserved;
  union {
    WORD wPrimitiveCount;
    WORD wStateCount;
  };
} D3DHAL_DP2COMMAND, *LPD3DHAL_DP2COMMAND;
````


## -struct-fields

### -field bCommand

Specifies a primitive to draw or a state change to process. This member can be one of the <a href="..\d3dhal\ne-d3dhal-_d3dhal_dp2operation.md">D3DHAL_DP2OPERATION</a> enumerated values. 


### -field bReserved

Reserved for system use and should be ignored by the driver.


### -field wPrimitiveCount

Specifies the number of primitives to process. This member is valid when <b>bCommand</b> is not either of D3DDP2OP_RENDERSTATE or D3DDP2OP_TEXTURESTAGESTATE.


### -field wStateCount

Specifies the number of state changes to process. This member is valid when <b>bCommand</b> is one of D3DDP2OP_RENDERSTATE or D3DDP2OP_TEXTURESTAGESTATE.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dhal.h (include D3dhal.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>D3DDP2OP_RENDERSTATE</dt>
<dt>D3DDP2OP_TEXTURESTAGESTATE</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ne-d3dhal-_d3dhal_dp2operation.md">D3DHAL_DP2OPERATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2COMMAND structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

