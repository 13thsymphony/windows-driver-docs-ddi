---
UID: NF.wdm.IoCompleteRequest
title: IoCompleteRequest macro
author: windows-driver-content
description: The IoCompleteRequest routine indicates that the caller has completed all processing for a given I/O request and is returning the given IRP to the I/O manager.
old-location: kernel\iocompleterequest.htm
old-project: kernel
ms.assetid: 59252b09-00ee-4a39-9849-5ce840ee16a7
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IoCompleteRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoCompleteRequest
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: CompleteRequest, CompleteRequestStatusCheck, DoubleCompletion, IoAllocateComplete, IoBuildFsdComplete, IoSetCompletionExCompleteIrp, IrpProcessingComplete, MarkIrpPending, PendedCompletedRequest, PendedCompletedRequest2, PendedCompletedRequest3, PendedCompletedRequestEx, PnpIrpCompletion, SpinLockSafe, WmiComplete, HwStorPortProhibitedDDIs, SpinLockSafe(storport)
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

# IoCompleteRequest macro



## -description
The <b>IoCompleteRequest</b> routine indicates that the caller has completed all processing for a given I/O request and is returning the given IRP to the I/O manager.



## -syntax

````
VOID IoCompleteRequest(
  _In_ PIRP  Irp,
  _In_ CCHAR PriorityBoost
);
````


## -parameters

### -param Irp [in]

Pointer to the IRP to be completed.


### -param PriorityBoost [in]

Specifies a system-defined constant by which to increment the run-time priority of the original thread that requested the operation. This value is IO_NO_INCREMENT if the original thread requested an operation the driver could complete quickly (so the requesting thread is not compensated for its assumed wait for I/O to be completed) or if the IRP is completed with an error. Otherwise, the set of <i>PriorityBoost</i> constants are device-type-specific. See Ntddk.h or Wdm.h for these constants.


## -remarks
When a driver has finished all processing for a given IRP, it calls <b>IoCompleteRequest</b>. The I/O manager checks the IRP to determine whether any higher-level drivers have set up an <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> routine for the IRP. If so, each <i>IoCompletion</i> routine is called, in turn, until every layered driver in the chain has completed the IRP.

When all drivers have completed a given IRP, the I/O manager returns status to the original requester of the operation. Note that a higher-level driver that sets up a driver-created IRP must supply an <i>IoCompletion</i> routine to release the IRP it created.

Never call <b>IoCompleteRequest</b> while holding a spin lock. Attempting to complete an IRP while holding a spin lock can cause deadlocks.


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
<a href="devtest.wdm_completerequest">CompleteRequest</a>, <a href="devtest.wdm_completerequeststatuscheck">CompleteRequestStatusCheck</a>, <a href="devtest.wdm_doublecompletion">DoubleCompletion</a>, <a href="devtest.wdm_ioallocatecomplete">IoAllocateComplete</a>, <a href="devtest.wdm_iobuildfsdcomplete">IoBuildFsdComplete</a>, <a href="devtest.wdm_iosetcompletionexcompleteirp">IoSetCompletionExCompleteIrp</a>, <a href="devtest.wdm_irpprocessingcomplete">IrpProcessingComplete</a>, <a href="devtest.wdm_markirppending">MarkIrpPending</a>, <a href="devtest.wdm_pendedcompletedrequest">PendedCompletedRequest</a>, <a href="devtest.wdm_pendedcompletedrequest2">PendedCompletedRequest2</a>, <a href="devtest.wdm_pendedcompletedrequest3">PendedCompletedRequest3</a>, <a href="devtest.wdm_pendedcompletedrequestex">PendedCompletedRequestEx</a>, <a href="devtest.wdm_pnpirpcompletion">PnpIrpCompletion</a>, <a href="devtest.wdm_spinlocksafe">SpinLockSafe</a>, <a href="devtest.wdm_wmicomplete">WmiComplete</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>, <a href="devtest.storport_spinlocksafe">SpinLockSafe(storport)</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.iosetcompletionroutine">IoSetCompletionRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoCompleteRequest routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

