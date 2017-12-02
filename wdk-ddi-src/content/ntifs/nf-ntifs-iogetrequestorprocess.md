---
UID: NF.ntifs.IoGetRequestorProcess
title: IoGetRequestorProcess
author: windows-driver-content
description: The IoGetRequestorProcess routine returns a process pointer for the thread that originally requested a given I/O operation.
old-location: ifsk\iogetrequestorprocess.htm
old-project: ifsk
ms.assetid: 456e2354-1362-43f7-a2b0-3b3bec49b522
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IoGetRequestorProcess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoGetRequestorProcess
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
req.iface: 
---

# IoGetRequestorProcess function



## -description
<p>The <b>IoGetRequestorProcess</b> routine returns a process pointer for the thread that originally requested a given I/O operation.</p>


## -syntax

````
PEPROCESS IoGetRequestorProcess(
  _In_ PIRP Irp
);
````


## -parameters
<dl>

### -param Irp [in]

<dd>
<p>A pointer to the I/O request packet (IRP) for the I/O operation.</p>
</dd>
</dl>

## -returns
<p><b>IoGetRequestorProcess</b> returns a process pointer for the thread that requested the I/O operation. If the IRP is not associated with any thread, <b>IoGetRequestorProcess</b> returns <b>NULL</b>. </p>

## -remarks
<p>Staring with Windows Vista. <b>IoGetRequestorProcess</b> returns a pointer to the process to which the thread is currently attached. For IRPs queued for file objects, such as for completion port I/O, <b>IoGetRequestorProcess</b> returns a pointer to the issuing process. If no thread is attached,  <b>IoGetRequestorProcess</b> returns a pointer to the process that created the thread.</p>

<p>On  Windows XP, <b>IoGetRequestorProcess</b> returns a pointer to the process to which the thread is currently attached.<div class="alert"><b>Note</b>  On Windows XP, in cases where an IRP contains a non-NULL thread but has no thread attached, <b>IoGetRequestorProcess</b> will attempt to access  the process information for an undefined thread. This presents a possible bug check condition if <b>IoGetRequestorProcess</b> is called without exception handling or at too high of an IRQL.</div>
<div> </div>
</p>

<p>Prior to Windows XP, <b>IoGetRequestorProcess</b> returns a pointer to the process that created the thread. </p>

<p>An IRP is automatically associated with a thread if it is issued by the I/O Manager or obtained by calling <a href="..\wdm\nf-wdm-iobuildasynchronousfsdrequest.md">IoBuildAsynchronousFsdRequest</a>, <a href="..\wdm\nf-wdm-iobuildsynchronousfsdrequest.md">IoBuildSynchronousFsdRequest</a>, or <a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a>. </p>

<p>For more information about using system threads and managing synchronization within a nonarbitrary thread context, see <a href="kernel.driver_threads__dispatcher_objects__and_resources">Driver Threads, Dispatcher Objects, and Resources</a>. </p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
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
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-iobuildasynchronousfsdrequest.md">IoBuildAsynchronousFsdRequest</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iobuildsynchronousfsdrequest.md">IoBuildSynchronousFsdRequest</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-iogetrequestorprocessid.md">IoGetRequestorProcessId</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoGetRequestorProcess routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
