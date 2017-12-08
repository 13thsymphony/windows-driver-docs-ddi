---
UID: NS.D3DKMTHK._D3DKMT_GETCONTEXTSCHEDULINGPRIORITY
title: _D3DKMT_GETCONTEXTSCHEDULINGPRIORITY
author: windows-driver-content
description: The D3DKMT_GETDEVICESCHEDULINGPRIORITY structure describes parameters for retrieving scheduling priority for a device context.
old-location: display\d3dkmt_getcontextschedulingpriority.htm
old-project: display
ms.assetid: ef60ba1c-6fff-4553-ba1c-97abbe48fed9
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DKMT_GETCONTEXTSCHEDULINGPRIORITY, D3DKMT_GETCONTEXTSCHEDULINGPRIORITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_GETCONTEXTSCHEDULINGPRIORITY
req.alt-loc: d3dkmthk.h
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

# _D3DKMT_GETCONTEXTSCHEDULINGPRIORITY structure



## -description
The D3DKMT_GETDEVICESCHEDULINGPRIORITY structure describes parameters for retrieving scheduling priority for a device context. 


## -syntax

````
typedef struct _D3DKMT_GETCONTEXTSCHEDULINGPRIORITY {
  D3DKMT_HANDLE hContext;
  INT           Priority;
} D3DKMT_GETCONTEXTSCHEDULINGPRIORITY;
````


## -struct-fields

### -field hContext

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the device context to retrieve scheduling priority for.

### -field Priority

[out] The priority level that is retrieved for the device context.

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
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dkmtgetcontextschedulingpriority">D3DKMTGetContextSchedulingPriority</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_GETCONTEXTSCHEDULINGPRIORITY structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
