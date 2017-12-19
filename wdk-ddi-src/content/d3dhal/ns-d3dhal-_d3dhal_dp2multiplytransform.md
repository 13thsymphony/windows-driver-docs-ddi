---
UID: NS.D3DHAL._D3DHAL_DP2MULTIPLYTRANSFORM
title: _D3DHAL_DP2MULTIPLYTRANSFORM
author: windows-driver-content
description: DirectX 8.0 and later versions only. The D3DHAL_DP2MULTIPLYTRANSFORM structure is used to modify the transform matrix for D3dDrawPrimitives2.
old-location: display\d3dhal_dp2multiplytransform.htm
old-project: display
ms.assetid: 3c7c0d40-a51e-4656-b262-233f0af8db0f
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DHAL_DP2MULTIPLYTRANSFORM, D3DHAL_DP2MULTIPLYTRANSFORM
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
req.alt-api: D3DHAL_DP2MULTIPLYTRANSFORM
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

# _D3DHAL_DP2MULTIPLYTRANSFORM structure



## -description

   DirectX 8.0 and later versions only.
   

The D3DHAL_DP2MULTIPLYTRANSFORM structure is used to modify the transform matrix for <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.



## -syntax

````
typedef struct _D3DHAL_DP2MULTIPLYTRANSFORM {
  D3DTRANSFORMSTATETYPE xfrmType;
  D3DMATRIX             matrix;
} D3DHAL_DP2MULTIPLYTRANSFORM, *LPD3DHAL_DP2MULTIPLYTRANSFORM;
````


## -struct-fields

### -field xfrmType

Specifies the current transform being modified.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DTRANSFORMSTATE_PROJECTION

</td>
<td>
Specifies the current projection transformation.

</td>
</tr>
<tr>
<td>
D3DTRANSFORMSTATE_VIEW

</td>
<td>
Specifies the current view transformation.

</td>
</tr>
<tr>
<td>
D3DTRANSFORMSTATE_WORLD

</td>
<td>
Specifies the current world transformation.

</td>
</tr>
</table>
 


### -field matrix

Specifies the matrix used to modify the current transform.


## -remarks
This structure is used with hardware transform and lighting and is used by the Direct3D runtime to inform the driver about modifications to the various transformation matrices.


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
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="display.d3dhal_dp2settransform">D3DHAL_DP2SETTRANSFORM</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2MULTIPLYTRANSFORM structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

