---
UID: NS:d3dkmddi._DXGKARG_SETPOINTERPOSITION
title: _DXGKARG_SETPOINTERPOSITION
author: windows-driver-content
description: The DXGKARG_SETPOINTERPOSITION structure describes where and how to display the mouse pointer.
old-location: display\dxgkarg_setpointerposition.htm
old-project: display
ms.assetid: a5670b3e-a96b-439c-ac1a-644611110700
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGKARG_SETPOINTERPOSITION, DXGKARG_SETPOINTERPOSITION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_SETPOINTERPOSITION
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: DXGKARG_SETPOINTERPOSITION
---

# _DXGKARG_SETPOINTERPOSITION structure



## -description
The DXGKARG_SETPOINTERPOSITION structure describes where and how to display the mouse pointer. 



## -syntax

````
typedef struct _DXGKARG_SETPOINTERPOSITION {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  INT                            X;
  INT                            Y;
  DXGK_SETPOINTERPOSITIONFLAGS   Flags;
} DXGKARG_SETPOINTERPOSITION;
````


## -struct-fields

### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the mouse pointer is located on. 


### -field X

[in] The column, in pixels, that the mouse pointer is located on from the top left.


### -field Y

[in] The row, in pixels, that the mouse pointer is located on from the top left.


### -field Flags

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_setpointerpositionflags.md">DXGK_SETPOINTERPOSITIONFLAGS</a> structure that identifies, in bit-field flags, information about the mouse pointer.


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
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_setpointerpositionflags.md">DXGK_SETPOINTERPOSITIONFLAGS</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setpointerposition.md">DxgkDdiSetPointerPosition</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_SETPOINTERPOSITION structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

