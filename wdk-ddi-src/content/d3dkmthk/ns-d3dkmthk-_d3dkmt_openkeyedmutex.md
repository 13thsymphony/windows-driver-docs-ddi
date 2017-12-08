---
UID: NS.D3DKMTHK._D3DKMT_OPENKEYEDMUTEX
title: _D3DKMT_OPENKEYEDMUTEX
author: windows-driver-content
description: The D3DKMT_OPENKEYEDMUTEX structure describes a keyed mutex that the D3DKMTOpenKeyedMutex function opens.
old-location: display\d3dkmt_openkeyedmutex.htm
old-project: display
ms.assetid: c5200822-b393-4ba1-8d2a-d4ab98ffcf1d
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DKMT_OPENKEYEDMUTEX, D3DKMT_OPENKEYEDMUTEX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_OPENKEYEDMUTEX is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_OPENKEYEDMUTEX
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

# _D3DKMT_OPENKEYEDMUTEX structure



## -description
The D3DKMT_OPENKEYEDMUTEX structure describes a keyed mutex that the <a href="display.d3dkmtopenkeyedmutex">D3DKMTOpenKeyedMutex</a> function opens. 


## -syntax

````
typedef struct _D3DKMT_OPENKEYEDMUTEX {
  D3DKMT_HANDLE hSharedHandle;
  D3DKMT_HANDLE hKeyedMutex;
} D3DKMT_OPENKEYEDMUTEX;
````


## -struct-fields

### -field hSharedHandle

[in] A D3DKMT_HANDLE data type that represents a kernel-mode shared global handle to the keyed mutex object. 

### -field hKeyedMutex

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the keyed mutex object in the current process. 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
D3DKMT_OPENKEYEDMUTEX is supported beginning with the Windows 7 operating system. 
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
<a href="display.d3dkmtopenkeyedmutex">D3DKMTOpenKeyedMutex</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_OPENKEYEDMUTEX structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
