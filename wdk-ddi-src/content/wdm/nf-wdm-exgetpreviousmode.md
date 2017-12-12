---
UID: NF.wdm.ExGetPreviousMode
title: ExGetPreviousMode function
author: windows-driver-content
description: The ExGetPreviousMode routine returns the previous processor mode for the current thread.
old-location: kernel\exgetpreviousmode.htm
old-project: kernel
ms.assetid: 0f4c7bc2-a29d-4b0c-81c3-01cdfefa1322
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: ExGetPreviousMode
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
req.alt-api: ExGetPreviousMode
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
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# ExGetPreviousMode function



## -description
The <b>ExGetPreviousMode</b> routine returns the previous processor mode for the current thread.



## -syntax

````
KPROCESSOR_MODE ExGetPreviousMode(void);
````


## -parameters


## -returns
<b>ExGetPreviousMode</b> returns a <b>KPROCESSOR_MODE</b> value, one of <b>KernelMode</b> or <b>UserMode</b>. This value specifies the previous processor mode for the current thread.

<b>ExGetPreviousMode</b> returns a <b>KPROCESSOR_MODE</b> value, one of <b>KernelMode</b> or <b>UserMode</b>. This value specifies the previous processor mode for the current thread.

<b>ExGetPreviousMode</b> returns a <b>KPROCESSOR_MODE</b> value, one of <b>KernelMode</b> or <b>UserMode</b>. This value specifies the previous processor mode for the current thread.


## -remarks
If an I/O request can originate either in user mode or kernel mode and the caller passes pointers to data structures used for I/O, the driver must be able to determine whether the caller's pointers are valid in user mode or kernel mode.

If drivers are processing I/O requests using the normal IRP-based I/O dispatch method, they can determine the previous processor mode by checking the <i>RequestorMode</i> parameter in the IRP header. (The <i>RequestorMode</i> parameter is set by the I/O manager.)

Alternatively, <b>ExGetPreviousMode</b> can be used to determine the previous processor mode. This routine is particularly useful in situations where a previous mode parameter is not available, for example, in a file driver that uses fast I/O.


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
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.kegetcurrentthread">KeGetCurrentThread</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExGetPreviousMode routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

