---
UID: NS.D3DUMDDI._D3DDDICB_LOCK2
title: _D3DDDICB_LOCK2
author: windows-driver-content
description: D3DDDICB_LOCK2 describes parameters for locking an allocation.
old-location: display\d3dddicb_lock2.htm
old-project: display
ms.assetid: 71E2E98D-4C97-4C04-A379-88C2A7CC8428
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DDDICB_LOCK2, D3DDDICB_LOCK2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDICB_LOCK2
req.alt-loc: d3dumddi.h
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

# _D3DDDICB_LOCK2 structure



## -description
<b>D3DDDICB_LOCK2</b> describes parameters for locking an allocation.



## -syntax

````
typedef struct _D3DDDICB_LOCK2 {
  D3DKMT_HANDLE       hAllocation;
  D3DDDICB_LOCK2FLAGS Flags;
  PVOID               pData;
} D3DDDICB_LOCK2;
````


## -struct-fields

### -field hAllocation

[in] A driver specified <b>D3DKMT_HANDLE</b> to the allocation to lock.


### -field Flags

A set of flags to pass to the <a href="display.d3dkmtlock2">Lock2</a> kernel function which will determine how the allocation is locked. See <a href="display.d3dddicb_lock2flags">D3DDDICB_LOCK2FLAGS</a> for details.


### -field pData

[out] A CPU virtual address pointing a valid memory location pointing to the CPU backing store or the GPU frame buffer.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

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
<a href="display.d3dkmtlock2">Lock2</a>
</dt>
<dt>
<a href="display.d3dddicb_lock2flags">D3DDDICB_LOCK2FLAGS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_LOCK2 structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

