---
UID: NS.D3DUMDDI.D3DDDICB_LOGUMDMARKER
title: D3DDDICB_LOGUMDMARKER
author: windows-driver-content
description: Specifies info about the location of an Event Tracing for Windows (ETW) marker event that the user-mode display driver has defined.
old-location: display\d3dddicb_logumdmarker.htm
old-project: display
ms.assetid: D953C714-6C11-4F8A-A7F9-416A00C518B4
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3DDDICB_LOGUMDMARKER, D3DDDICB_LOGUMDMARKER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDICB_LOGUMDMARKER
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

# D3DDDICB_LOGUMDMARKER structure



## -description
Specifies info about the location of an Event Tracing for Windows (ETW) marker event that the user-mode display driver has defined.



## -syntax

````
typedef struct D3DDDICB_LOGUMDMARKER {
  HANDLE  hContext;
  UINT64  APISequenceNumber;
  INT     Index;
  INT     StringIndex;
  LPCWSTR Info;
} D3DDDICB_LOGUMDMARKER;
````


## -struct-fields

### -field hContext

[in] A handle to a Direct3D context that signals ETW marker events. This is also the context that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a> function will be called on.


### -field APISequenceNumber

The API sequence number that the marker event is associated with.


### -field Index

Indicates which API sequence call caused this marker event. If zero, the marker event corresponds to the latest API sequence number after a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setmarker.md">pfnSetMarker</a> function. If 1, the marker event is located at the following API sequence number. And so on.

Should be -1 if no time stamps are associated with this marker event.


### -field StringIndex

The offset, in bytes, of the string table entry pointed to by <b>Info</b>. Can be negative if the string is passed along with the marker event.


### -field Info

A custom text string embedded in the ETW packet. Can be <b>NULL</b>.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setmarker.md">pfnSetMarker</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_LOGUMDMARKER structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

