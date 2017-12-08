---
UID: NS.D3DKMTHK._D3DKMT_OUTPUTDUPLPRESENT
title: _D3DKMT_OUTPUTDUPLPRESENT
author: windows-driver-content
description: Describes a Desktop Duplication API swapchain present operation.
old-location: display\d3dkmt_outputduplpresent.htm
old-project: display
ms.assetid: 1820e11c-0888-4d6d-aa75-b895c863eb43
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DKMT_OUTPUTDUPLPRESENT, D3DKMT_OUTPUTDUPLPRESENT
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
req.alt-api: D3DKMT_OUTPUTDUPLPRESENT
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

# _D3DKMT_OUTPUTDUPLPRESENT structure



## -description
Describes a <a href="direct3ddxgi.desktop_dup_api">Desktop Duplication API</a> swapchain present operation.


## -syntax

````
typedef struct _D3DKMT_OUTPUTDUPLPRESENT {
  D3DKMT_HANDLE                  hContext;
  D3DKMT_HANDLE                  hSource;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  ULONG                          BroadcastContextCount;
  D3DKMT_HANDLE                  BroadcastContext[D3DDDI_MAX_BROADCAST_CONTEXT];
  D3DKMT_PRESENT_RGNS            PresentRegions;
  D3DKMT_OUTPUTDUPLPRESENTFLAGS  Flags;
} D3DKMT_OUTPUTDUPLPRESENT;
````


## -struct-fields

### -field hContext

[in] A D3DKMT_HANDLE data type that represents a handle to the context.

### -field hSource

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the source allocation to be displayed.

### -field VidPnSourceId

The zero-based identification number of a video present source in a path of a video present network (VidPN) topology.

### -field BroadcastContextCount

[in] Specifies the number of contexts.

### -field BroadcastContext

[in] A D3DKMT_HANDLE data type that represents the broadcast context.

### -field PresentRegions

[in] Dirty and move regions, of type <a href="display.d3dkmt_present_rgns">D3DKMT_PRESENT_RGNS</a>.

### -field Flags

[in] A bitwise-OR combination of values from the <a href="display.d3dkmt_outputduplpresentflags">D3DKMT_OUTPUTDUPLPRESENTFLAGS</a> enumeration that describe options for the present operation.

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

## -see-also
<dl>
<dt>
<a href="display.d3dkmt_outputduplpresentflags">D3DKMT_OUTPUTDUPLPRESENTFLAGS</a>
</dt>
<dt>
<a href="display.d3dkmt_present_rgns">D3DKMT_PRESENT_RGNS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_OUTPUTDUPLPRESENT structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
