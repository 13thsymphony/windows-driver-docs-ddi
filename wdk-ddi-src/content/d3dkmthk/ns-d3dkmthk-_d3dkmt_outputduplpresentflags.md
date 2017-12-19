---
UID: NS.D3DKMTHK._D3DKMT_OUTPUTDUPLPRESENTFLAGS
title: _D3DKMT_OUTPUTDUPLPRESENTFLAGS
author: windows-driver-content
description: Describes options for a Desktop Duplication API swapchain present operation.
old-location: display\d3dkmt_outputduplpresentflags.htm
old-project: display
ms.assetid: d80bcf24-4d53-4ec9-897d-d3243c7fda25
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DKMT_OUTPUTDUPLPRESENTFLAGS, D3DKMT_OUTPUTDUPLPRESENTFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_OUTPUTDUPLPRESENTFLAGS
req.alt-loc: D3dkmthk.h
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

# _D3DKMT_OUTPUTDUPLPRESENTFLAGS structure



## -description
Describes options for a <a href="direct3ddxgi.desktop_dup_api">Desktop Duplication API</a> swapchain present operation.



## -syntax

````
typedef struct _D3DKMT_OUTPUTDUPLPRESENTFLAGS {
  union {
    struct {
      UINT ProtectedContentBlankedOut  :1;
      UINT RemoteSession  :1;
      UINT FullScreenPresent  :1;
      UINT Reserved  :29;
    };
    UINT   Value;
  };
} D3DKMT_OUTPUTDUPLPRESENTFLAGS;
````


## -struct-fields

### -field ProtectedContentBlankedOut

Specifies whether the desktop image might contain protected content that was already blanked out (black) in the desktop image.

<b>TRUE</b> if protected content was already blanked out; otherwise, <b>FALSE</b>.

The application can use this information to notify the remote user that some of the desktop content might be protected and therefore not visible.


### -field RemoteSession

Specifies if the present operation is directed to a remote session

<b>TRUE</b> if the present operation is directed to a remote session; otherwise, <b>FALSE</b>.

If <b>TRUE</b>, the present operation will go through a GDI path.


### -field FullScreenPresent

Specifies if the present operation is to the full screen.

<b>TRUE</b> if the present operation is to the full screen; otherwise, <b>FALSE</b>.


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 29 bits (0xFFFFFFF8) of the 32-bit <b>Value</b> member to zeros.




### -field Value

A 32-bit value that identifies the DDA present options.


## -remarks


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
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>