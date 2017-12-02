---
UID: NF.wdm.ZwQuerySymbolicLinkObject
title: ZwQuerySymbolicLinkObject
author: windows-driver-content
description: The ZwQuerySymbolicLinkObject routine returns a Unicode string that contains the target of a symbolic link.
old-location: kernel\zwquerysymboliclinkobject.htm
old-project: kernel
ms.assetid: 0294c840-2912-4137-886f-832e9f21bbea
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: ZwQuerySymbolicLinkObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwQuerySymbolicLinkObject,NtQuerySymbolicLinkObject
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
req.iface: 
req.product: Windows 10 or later.
---

# ZwQuerySymbolicLinkObject function



## -description
<p>The <b>ZwQuerySymbolicLinkObject</b> routine returns a Unicode string that contains the target of a symbolic link.</p>


## -syntax

````
NTSTATUS ZwQuerySymbolicLinkObject(
  _In_      HANDLE          LinkHandle,
  _Inout_   PUNICODE_STRING LinkTarget,
  _Out_opt_ PULONG          ReturnedLength
);
````


## -parameters
<dl>

### -param LinkHandle [in]

<dd>
<p>Handle to the symbolic-link object that you want to query. This handle is created by a successful call to <a href="..\wdm\nf-wdm-zwopensymboliclinkobject.md">ZwOpenSymbolicLinkObject</a>. </p>
</dd>

### -param LinkTarget [in, out]

<dd>
<p>Pointer to an initialized Unicode string that receives the target of the symbolic link.</p>
</dd>

### -param ReturnedLength [out, optional]

<dd>
<p> contains the maximum number of bytes to copy into the Unicode string at <i>LinkTarget</i>. On output, the unsigned long integer contains the length of the Unicode string naming the target of the symbolic link. </p>
</dd>
</dl>

## -returns
<p><b>ZwQuerySymbolicLinkObject</b> returns either STATUS_SUCCESS to indicate the routine completed without error or STATUS_BUFFER_TOO_SMALL if the Unicode string provided at <i>LinkTarget</i> is too small to hold the returned string.</p>

## -remarks
<p>Before calling this routine, driver writers must ensure that the Unicode string at <i>LinkTarget </i>has been properly initialized and a buffer for the string has been allocated. The <b>MaximumLength</b> and <b>Buffer</b> members of the Unicode string must be set before calling <b>ZwQuerySymbolicLinkObject</b> or the call will fail.</p>

<p>If <b>ZwQuerySymbolicLinkObject</b> returns STATUS_BUFFER_TOO_SMALL drivers should examine the value returned at <i>ReturnedLength</i>. The number returned in this variable indicates the maximum length that the Unicode string for the target of the symbolic link.</p>

<p>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 2000 and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopensymboliclinkobject.md">ZwOpenSymbolicLinkObject</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwQuerySymbolicLinkObject routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
