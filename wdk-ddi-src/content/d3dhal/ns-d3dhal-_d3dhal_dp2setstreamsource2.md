---
UID: NS:d3dhal._D3DHAL_DP2SETSTREAMSOURCE2
title: _D3DHAL_DP2SETSTREAMSOURCE2
author: windows-driver-content
description: DirectX 9.0 and later versions only. The D3DHAL_DP2SETSTREAMSOURCE2 structure is used to bind a portion of a vertex stream source to a vertex buffer for D3dDrawPrimitives2.
old-location: display\d3dhal_dp2setstreamsource2.htm
old-project: display
ms.assetid: a8e1ea01-2050-413a-991f-55c29977b6dd
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DHAL_DP2SETSTREAMSOURCE2, D3DHAL_DP2SETSTREAMSOURCE2, *LPD3DHAL_DP2SETSTREAMSOURCE2
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
req.alt-api: D3DHAL_DP2SETSTREAMSOURCE2
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
req.typenames: D3DHAL_DP2SETSTREAMSOURCE2
---

# _D3DHAL_DP2SETSTREAMSOURCE2 structure



## -description

   DirectX 9.0 and later versions only.
   

The D3DHAL_DP2SETSTREAMSOURCE2 structure is used to bind a portion of a vertex stream source to a vertex buffer for <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.



## -syntax

````
typedef struct _D3DHAL_DP2SETSTREAMSOURCE2 {
  DWORD dwStream;
  DWORD dwVBHandle;
  DWORD dwOffset;
  DWORD dwStride;
} D3DHAL_DP2SETSTREAMSOURCE2, *LPD3DHAL_DP2SETSTREAMSOURCE2;
````


## -struct-fields

### -field dwStream

Specifies the stream being bound. It has a value between zero and the maximum number of streams specified by the driver.


### -field dwVBHandle

Specifies the vertex buffer handle. It is legal for the vertex buffer handle to be zero, in which case the stream is no longer bound to a vertex buffer.


### -field dwOffset

Specifies the offset of the first vertex size in bytes.


### -field dwStride

Specifies the vertex size in bytes.


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
<dt>D3DDP2OP_SETSTREAMSOURCE2</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2SETSTREAMSOURCE2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

