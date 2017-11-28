---
UID: NF.ntddk.IoAssignArcName
title: IoAssignArcName
author: windows-driver-content
description: The IoAssignArcName routine creates a symbolic link between the ARC name of a physical device and the name of the corresponding device object when it has been created.
old-location: kernel\ioassignarcname.htm
old-project: kernel
ms.assetid: ef8a132a-f593-4a25-bb9e-b4ed57801db2
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: IoAssignArcName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoAssignArcName
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: HwStorPortProhibitedDDIs
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
---

# IoAssignArcName function



## -description
<p>The <b>IoAssignArcName</b> routine creates a symbolic link between the ARC name of a physical device and the name of the corresponding device object when it has been created.</p>


## -syntax

````
VOID IoAssignArcName(
  _In_ PUNICODE_STRING ArcName,
  _In_ PUNICODE_STRING DeviceName
);
````


## -parameters
<dl>

### -param <i>ArcName</i> [in]

<dd>
<p>Pointer to a buffer containing the ARC name of the device. The ARC name must be a Unicode string.</p>
</dd>

### -param <i>DeviceName</i> [in]

<dd>
<p>Pointer to a buffer containing the name of the device object, representing the same device. The device object name must be a Unicode string. </p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>Drivers of hard disk devices need not call this routine. Drivers of other mass storage devices, including floppy, CD-ROM, and tape devices, should call <b>IoAssignArcName</b> during their initialization. </p>

<p>Drivers of hard disk devices need not call this routine. Drivers of other mass storage devices, including floppy, CD-ROM, and tape devices, should call <b>IoAssignArcName</b> during their initialization. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 2000.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoAssignArcName routine%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
