---
UID: NS.D3DHAL._D3DHAL_DP2SETTRANSFORM
title: _D3DHAL_DP2SETTRANSFORM
author: windows-driver-content
description: D3DHAL_DP2SETTRANSFORM structure is used to specify the transform state and matrix for D3dDrawPrimitives2.
old-location: display\d3dhal_dp2settransform.htm
old-project: display
ms.assetid: 7905f5bd-15f5-4b4f-bc00-91acb2371dc0
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DHAL_DP2SETTRANSFORM, D3DHAL_DP2SETTRANSFORM
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
req.alt-api: D3DHAL_DP2SETTRANSFORM
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

# _D3DHAL_DP2SETTRANSFORM structure



## -description
D3DHAL_DP2SETTRANSFORM structure is used to specify the transform state and matrix for <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.



## -syntax

````
typedef struct _D3DHAL_DP2SETTRANSFORM {
  D3DTRANSFORMSTATETYPE xfrmType;
  D3DMATRIX             matrix;
} D3DHAL_DP2SETTRANSFORM, *LPD3DHAL_DP2SETTRANSFORM;
````


## -struct-fields

### -field xfrmType

Specifies the type of transform being done.

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
Specifies a projection transformation.

</td>
</tr>
<tr>
<td>
D3DTRANSFORMSTATE_VIEW

</td>
<td>
Specifies a view transformation.

</td>
</tr>
<tr>
<td>
D3DTRANSFORMSTATE_WORLD

</td>
<td>
Specifies a world transformation.

</td>
</tr>
</table>
 


### -field matrix

Specifies the matrix used to perform the transform. 


## -remarks
This structure is used with hardware transform and lighting and is used by the Direct3D runtime to inform the driver about the various transformation matrices.


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
<a href="display.d3dhal_dp2multiplytransform">D3DHAL_DP2MULTIPLYTRANSFORM</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2SETTRANSFORM structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

