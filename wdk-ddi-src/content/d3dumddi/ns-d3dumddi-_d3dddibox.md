---
UID: NS.D3DUMDDI._D3DDDIBOX
title: _D3DDDIBOX
author: windows-driver-content
description: Describes the bounds of a volume texture.
old-location: display\d3dddibox.htm
old-project: display
ms.assetid: 3CE49C9F-EFFC-4F43-A939-623B28FD5EFB
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DDDIBOX, D3DDDIBOX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIBOX
req.alt-loc: D3dumddi.h
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

# _D3DDDIBOX structure



## -description
Describes the bounds of a volume texture.



## -syntax

````
typedef struct _D3DDDIBOX {
  UINT Left;
  UINT Top;
  UINT Right;
  UINT Bottom;
  UINT Front;
  UINT Back;
} D3DDDIBOX;
````


## -struct-fields

### -field Left

[in] The position of the left side of the box on the x-axis.


### -field Top

[in] The position of the top of the box on the y-axis.


### -field Right

[in] The position of the right side of the box on the x-axis.


### -field Bottom

[in] The position of the bottom of the box on the y-axis.


### -field Front


      [in] The position of the front of the box on the z-axis.


### -field Back

[in] The position of the back of the box on the z-axis.


## -remarks
The height of the volume equals the value in the <b>Bottom</b> member minus the value in the <b>Top</b> member (that is, height = bottom – top). 

The width of the volume equals the value in the <b>Right</b> member minus the value in the <b>Left</b> member (that is, width = right – left). 

The depth of the volume equals the value in the <b>Back</b> member minus the value in the <b>Front</b> member (that is, depth = back – front). 


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

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