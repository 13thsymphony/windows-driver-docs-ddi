---
UID: NS.D3DKMDDI._DXGKARGCB_GETHANDLEDATA
title: _DXGKARGCB_GETHANDLEDATA
author: windows-driver-content
description: The DXGKARGCB_GETHANDLEDATA structure describes a handle to private data.
old-location: display\dxgkargcb_gethandledata.htm
old-project: display
ms.assetid: 22a03f0b-71c3-4942-b5da-ca588e17d346
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGKARGCB_GETHANDLEDATA, DXGKARGCB_GETHANDLEDATA
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
req.alt-api: DXGKARGCB_GETHANDLEDATA
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
---

# _DXGKARGCB_GETHANDLEDATA structure



## -description
The DXGKARGCB_GETHANDLEDATA structure describes a handle to private data.



## -syntax

````
typedef struct _DXGKARGCB_GETHANDLEDATA {
  D3DKMT_HANDLE             hObject;
  DXGK_HANDLE_TYPE          Type;
  DXGKCB_GETHANDLEDATAFLAGS Flags;
} DXGKARGCB_GETHANDLEDATA;
````


## -struct-fields

### -field hObject

[in] A handle to the private data. This handle is the kernel-mode handle that the Microsoft DirectX graphics kernel subsystem (which is part of <i>Dxgkrnl.sys</i>) assigned for the private data.


### -field Type

[in] A DXGK_HANDLE_TYPE-typed value that indicates the type of handle to retrieve data about. This member can be one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DXGK_HANDLE_ALLOCATION (1)

</td>
<td>
The allocations belong to a resource.

</td>
</tr>
<tr>
<td>
DXGK_HANDLE_RESOURCE (2)

</td>
<td>
The <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> call is the result of the creation of the primary surface.

</td>
</tr>
</table>
 


### -field Flags

[in] A <a href="display.dxgkcb_gethandledataflags">DXGKCB_GETHANDLEDATAFLAGS</a> structure that indicates if allocations belong to a resource.


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
<a href="display.dxgkcb_gethandledataflags">DXGKCB_GETHANDLEDATAFLAGS</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_gethandledata.md">DxgkCbGetHandleData</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARGCB_GETHANDLEDATA structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

