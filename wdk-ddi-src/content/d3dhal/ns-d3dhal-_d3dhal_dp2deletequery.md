---
UID: NS.D3DHAL._D3DHAL_DP2DELETEQUERY
title: _D3DHAL_DP2DELETEQUERY
author: windows-driver-content
description: DirectX 9.0 and later versions only.
old-location: display\d3dhal_dp2deletequery.htm
old-project: display
ms.assetid: c125e21f-20be-42c1-ba24-b13f2475f02e
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DHAL_DP2DELETEQUERY, D3DHAL_DP2DELETEQUERY
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
req.alt-api: D3DHAL_DP2DELETEQUERY
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
---

# _D3DHAL_DP2DELETEQUERY structure



## -description

   DirectX 9.0 and later versions only.
   

One or more D3DHAL_DP2DELETEQUERY structures are parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="display.d3dhal_dp2command">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_DELETEQUERY, and are used to release resources for queries.



## -syntax

````
typedef struct _D3DHAL_DP2DELETEQUERY {
  DWORD dwQueryID;
} D3DHAL_DP2DELETEQUERY, *LPD3DHAL_DP2DELETEQUERY;
````


## -struct-fields

### -field dwQueryID

Identifies the query for which the driver releases resources.


## -remarks
The runtime uses D3DHAL_DP2DELETEQUERY to identify each query. The driver's <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback must process <b>wPrimitiveCount</b> D3DHAL_DP2DELETEQUERY structures from the command buffer. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure. The driver parses these structures and releases resources for the queries that they represent. 


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
<dt>D3DDP2OP_DELETEQUERY</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="display.d3dhal_dp2command">D3DHAL_DP2COMMAND</a>
</dt>
<dt>
<a href="display.d3dhal_dp2createquery">D3DHAL_DP2CREATEQUERY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2DELETEQUERY structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

