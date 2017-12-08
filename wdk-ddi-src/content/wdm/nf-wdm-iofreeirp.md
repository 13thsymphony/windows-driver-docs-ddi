---
UID: NF.wdm.IoFreeIrp
title: IoFreeIrp function
author: windows-driver-content
description: The IoFreeIrp routine releases a caller-allocated IRP from the caller's IoCompletion routine.
old-location: kernel\iofreeirp.htm
old-project: kernel
ms.assetid: 4a032d44-c6c2-4dce-97ea-28ac47f6ad6c
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: IoFreeIrp
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
req.alt-api: IoFreeIrp
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IoAllocateFree, IoBuildDeviceControlNoFree, IoBuildFsdFree, IoBuildSynchronousFsdRequestNoFree, HwStorPortProhibitedDDIs, IoFreeIrp
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

# IoFreeIrp function



## -description
The <b>IoFreeIrp</b> routine releases a caller-allocated IRP from the caller's <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> routine.


## -syntax

````
VOID IoFreeIrp(
  _In_ PIRP Irp
);
````


## -parameters

### -param Irp [in]

Pointer to the IRP that is to be released.

## -returns
None

## -remarks
This routine is the reciprocal to <a href="kernel.ioallocateirp">IoAllocateIrp</a> or <a href="kernel.iobuildasynchronousfsdrequest">IoBuildAsynchronousFsdRequest</a>. The released IRP must have been allocated by the caller.

This routine also releases an IRP allocated with <a href="kernel.iomakeassociatedirp">IoMakeAssociatedIrp</a> in which the caller set up its <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> routine that returns STATUS_MORE_PROCESSING_REQUIRED for the associated IRP.

<b>IoFreeIrp</b> does not free any MDLs that might be attached to the IRP. The driver that frees the IRP must explicitly free these MDLs. In addition, if the physical pages that are described by an MDL are locked, the driver must unlock the pages before it frees the MDL. However, the driver does not need to explicitly unmap these pages. Instead, <a href="kernel.iofreemdl">IoFreeMdl</a> automatically unmaps the pages when it frees the MDL. For a code example that shows how to free an MDL chain, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.

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
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.wdm_ioallocatefree">IoAllocateFree</a>, <a href="devtest.wdm_iobuilddevicecontrolnofree">IoBuildDeviceControlNoFree</a>, <a href="devtest.wdm_iobuildfsdfree">IoBuildFsdFree</a>, <a href="devtest.wdm_iobuildsynchronousfsdrequestnofree">IoBuildSynchronousFsdRequestNoFree</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>, <a href="devtest.storport_iofreeirp">IoFreeIrp</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.ioallocateirp">IoAllocateIrp</a>
</dt>
<dt>
<a href="kernel.iobuildasynchronousfsdrequest">IoBuildAsynchronousFsdRequest</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a>
</dt>
<dt>
<a href="kernel.iomakeassociatedirp">IoMakeAssociatedIrp</a>
</dt>
<dt>
<a href="kernel.iosetcompletionroutine">IoSetCompletionRoutine</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoFreeIrp routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
