---
UID: NF:ntddk.PsGetCurrentThread
title: PsGetCurrentThread function
author: windows-driver-content
description: The PsGetCurrentThread routine identifies the current thread.
old-location: kernel\psgetcurrentthread.htm
old-project: kernel
ms.assetid: 132b30fe-21ef-48dc-8c69-02ccac563b87
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PsGetCurrentThread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PsGetCurrentThread
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
req.typenames: *PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT
---

# PsGetCurrentThread function



## -description
The <b>PsGetCurrentThread</b> routine identifies the current thread. 



## -syntax

````
PETHREAD PsGetCurrentThread(void);
````


## -parameters


## -returns
<b>PsGetCurrentThread</b> returns a pointer to the executive thread object that represents the currently executing thread. 

<b>PsGetCurrentThread</b> returns a pointer to the executive thread object that represents the currently executing thread. 

<b>PsGetCurrentThread</b> returns a pointer to the executive thread object that represents the currently executing thread. 


## -remarks
This macro 


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
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-kegetcurrentthread.md">KeGetCurrentThread</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-pscreatesystemthread.md">PsCreateSystemThread</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-psgetcurrentprocessid.md">PsGetCurrentProcessId</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-psissystemthread.md">PsIsSystemThread</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsGetCurrentThread routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

