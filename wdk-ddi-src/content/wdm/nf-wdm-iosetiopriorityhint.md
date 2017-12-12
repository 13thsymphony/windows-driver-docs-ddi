---
UID: NF.wdm.IoSetIoPriorityHint
title: IoSetIoPriorityHint function
author: windows-driver-content
description: The IoSetIoPriorityHint routine sets the priority hint value for an IRP.
old-location: kernel\iosetiopriorityhint.htm
old-project: kernel
ms.assetid: ecd4ed14-b9f2-45ff-a42b-5c67f1ccfd91
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: IoSetIoPriorityHint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoSetIoPriorityHint
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
req.irql: Any level
req.product: Windows 10 or later.
---

# IoSetIoPriorityHint function



## -description
The <b>IoSetIoPriorityHint</b> routine sets the <a href="https://msdn.microsoft.com/c34afff2-32f2-451b-ab16-ff048d5c3204">priority hint value</a> for an IRP.



## -syntax

````
NTSTATUS IoSetIoPriorityHint(
  _In_ PIRP             Irp,
  _In_ IO_PRIORITY_HINT PriorityHint
);
````


## -parameters

### -param Irp [in]

Specifies the IRP to set the priority hint value for.


### -param PriorityHint [in]

Specifies the <a href="kernel.io_priority_hint">IO_PRIORITY_HINT</a> value that indicates the new priority hint.


## -returns
<b>IoSetIoPriorityHint</b> returns STATUS_SUCCESS if the operation succeeds and the appropriate NTSTATUS value if the operation fails.


## -remarks
For more information about priority hints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565403">Using IRP Priority Hints</a>.


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
Available in Windows Vista and later versions of Windows.

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
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.io_priority_hint">IO_PRIORITY_HINT</a>
</dt>
<dt>
<a href="kernel.iogetiopriorityhint">IoGetIoPriorityHint</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoSetIoPriorityHint routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

