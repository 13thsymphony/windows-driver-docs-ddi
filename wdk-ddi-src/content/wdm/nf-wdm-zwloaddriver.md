---
UID: NF.wdm.ZwLoadDriver
title: ZwLoadDriver function
author: windows-driver-content
description: The ZwLoadDriver routine loads a driver into the system.
old-location: kernel\zwloaddriver.htm
old-project: kernel
ms.assetid: ab5afdc8-d4d3-4be0-a613-d92f1b847b27
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: ZwLoadDriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwLoadDriver,NtLoadDriver
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# ZwLoadDriver function



## -description
The <b>ZwLoadDriver</b> routine loads a driver into the system. 



## -syntax

````
NTSTATUS ZwLoadDriver(
  _In_ PUNICODE_STRING DriverServiceName
);
````


## -parameters

### -param DriverServiceName [in]

Pointer to a counted Unicode string that specifies a path to the driver's registry key, <b>\Registry\Machine\System\CurrentControlSet\Services\</b><i>DriverName</i>, where <i>DriverName</i> is the name of the driver. 


## -returns
<b>ZwLoadDriver</b> returns STATUS_SUCCESS or an appropriate error NTSTATUS value. 


## -remarks
<b>ZwLoadDriver</b> dynamically loads a device or file system driver into the currently running system. 

A minifilter should use <a href="ifsk.fltloadfilter">FltLoadFilter</a> instead of <b>ZwLoadDriver</b> to load a supporting minifilter.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.


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
Available in Windows XP and later versions of Windows.

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
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fltloadfilter">FltLoadFilter</a>
</dt>
<dt>
<a href="kernel.rtlinitunicodestring">RtlInitUnicodeString</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="kernel.zwunloaddriver">ZwUnloadDriver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwLoadDriver routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

