---
UID: NF:wdm.MmUnmapIoSpace
title: MmUnmapIoSpace function
author: windows-driver-content
description: The MmUnmapIoSpace routine unmaps a specified range of physical addresses previously mapped by MmMapIoSpace.
old-location: kernel\mmunmapiospace.htm
old-project: kernel
ms.assetid: 5963f34a-4315-46c3-9802-0b6a1b229e3f
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: MmUnmapIoSpace
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MmUnmapIoSpace
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=DISPATCH_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmUnmapIoSpace function



## -description
The <b>MmUnmapIoSpace</b> routine unmaps a specified range of physical addresses previously mapped by <b>MmMapIoSpace</b>.



## -syntax

````
VOID MmUnmapIoSpace(
  _In_ PVOID  BaseAddress,
  _In_ SIZE_T NumberOfBytes
);
````


## -parameters

### -param BaseAddress [in]

Pointer to the base virtual address to which the physical pages were mapped.


### -param NumberOfBytes [in]

Specifies the number of bytes that were mapped. 


## -returns
None


## -remarks
If a driver calls <b>MmMapIoSpace</b> during device start-up, it must call <b>MmUnmapIoSpace</b> when it receives a PnP stop-device or remove-device IRP for the same device object. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-mmmapiospace.md">MmMapIoSpace</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmUnmapIoSpace routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

