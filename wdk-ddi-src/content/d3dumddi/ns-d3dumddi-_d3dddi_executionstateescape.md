---
UID: NS.D3DUMDDI._D3DDDI_EXECUTIONSTATEESCAPE
title: _D3DDDI_EXECUTIONSTATEESCAPE
author: windows-driver-content
description: Specifies the state of the device.
old-location: display\d3dddi_executionstateescape.htm
old-project: display
ms.assetid: 9BA78743-91AA-4AAC-9FB3-CF8B30FC15AE
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DDDI_EXECUTIONSTATEESCAPE, D3DDDI_EXECUTIONSTATEESCAPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_EXECUTIONSTATEESCAPE
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

# _D3DDDI_EXECUTIONSTATEESCAPE structure



## -description
Specifies the state of the device.


## -syntax

````
typedef struct _D3DDDI_EXECUTIONSTATEESCAPE {
  D3DDDI_DEVICEEXECUTION_STATE State;
} D3DDDI_EXECUTIONSTATEESCAPE;
````


## -struct-fields

### -field State

[Out] A value of type <a href="display.d3dddi_deviceexecution_state">D3DDDI_DEVICEEXECUTION_STATE</a> that indicates the state of the device.

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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dddi_deviceexecution_state">D3DDDI_DEVICEEXECUTION_STATE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_EXECUTIONSTATEESCAPE structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
