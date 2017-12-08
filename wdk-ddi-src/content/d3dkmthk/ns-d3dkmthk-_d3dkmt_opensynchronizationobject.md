---
UID: NS.D3DKMTHK._D3DKMT_OPENSYNCHRONIZATIONOBJECT
title: _D3DKMT_OPENSYNCHRONIZATIONOBJECT
author: windows-driver-content
description: The D3DKMT_OPENSYNCHRONIZATIONOBJECT structure describes a synchronization object that the D3DKMTOpenSynchronizationObject function opens.
old-location: display\d3dkmt_opensynchronizationobject.htm
old-project: display
ms.assetid: 58e71ce5-29d0-4ee2-8d91-02230021110d
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DKMT_OPENSYNCHRONIZATIONOBJECT, D3DKMT_OPENSYNCHRONIZATIONOBJECT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_OPENSYNCHRONIZATIONOBJECT is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_OPENSYNCHRONIZATIONOBJECT
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

# _D3DKMT_OPENSYNCHRONIZATIONOBJECT structure



## -description
The D3DKMT_OPENSYNCHRONIZATIONOBJECT structure describes a synchronization object that the <a href="display.d3dkmtopensynchronizationobject">D3DKMTOpenSynchronizationObject</a> function opens. 


## -syntax

````
typedef struct _D3DKMT_OPENSYNCHRONIZATIONOBJECT {
  D3DKMT_HANDLE hSharedHandle;
  D3DKMT_HANDLE hSyncObject;
  UINT64        Reserved[8];
} D3DKMT_OPENSYNCHRONIZATIONOBJECT;
````


## -struct-fields

### -field hSharedHandle

[in] A shared handle to the synchronization object to be opened. 

### -field hSyncObject

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the kernel-mode synchronization object in the current process. 

### -field Reserved

[in] An array of 64-bit values that are reserved for future use. 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
D3DKMT_OPENSYNCHRONIZATIONOBJECT is supported beginning with the Windows 7 operating system. 
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
<a href="display.d3dkmtopensynchronizationobject">D3DKMTOpenSynchronizationObject</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_OPENSYNCHRONIZATIONOBJECT structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
