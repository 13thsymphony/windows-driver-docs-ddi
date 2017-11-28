---
UID: NC.storport.HW_STARTIO
title: HW_STARTIO
author: windows-driver-content
description: The Storport driver calls the HwStorStartIo routine one time for each incoming I/O request.
old-location: storage\hwstorstartio.htm
old-project: storage
ms.assetid: 73085ca7-a442-4c16-b1e3-6de048e7f1f7
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: STORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HwStorStartIo
req.alt-loc: Storport.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL (See Remarks section.)
req.iface: 
req.product: Windows 10 or later.
---

# HW_STARTIO callback



## -description
<p>The Storport driver calls the <b>HwStorStartIo</b> routine one time for each incoming I/O request.</p>


## -prototype

````
HW_STARTIO HwStorStartIo;

BOOLEAN HwStorStartIo(
   IN PVOID               DeviceExtension,
   IN PSCSI_REQUEST_BLOCK Srb
)
{ ... }
````


## -parameters
<dl>

### -param <i>DeviceExtension</i> 

<dd>
<p>A pointer to the miniport driver's per HBA storage area.</p>
</dd>

### -param <i>Srb</i> 

<dd>
<p>A pointer to the SCSI request block to be started. </p>
</dd>
</dl>

## -returns
<p><b>HwStorStartIo</b> returns <b>TRUE</b> if the request was successfully initiated. Otherwise, it returns <b>FALSE</b>. </p>

## -remarks
<p><b>HwStorStartIo</b> initiates an I/O operation. StorPort is designed to use miniport private data that is prepared in <a href="https://msdn.microsoft.com/library/windows/hardware/ff557369">HwStorBuildIo</a> and stored in either the <i>DeviceExtension</i> or <i>Srb-&gt;SrbExtension</i>.  Because <b>HwStorBuildIo</b> is called without spin locks, the best driver performance is achieved by preparing as much data  as possible in <b>HwStorBuildIo</b>.</p>

<p>Storport calls <b>HwStorStartIo</b> in the following ways:</p>

<p>For <a href="storage.storage_miniport_drivers">storage non-virtual miniport drivers</a>, depending on the value of <b>SynchronizationModel</b> set in <a href="https://msdn.microsoft.com/library/windows/hardware/ff567785">PORT_CONFIGURATION_INFORMATION</a>, Storport always calls <b>HwStorStartIo</b> the same IRQL and uses an internal spin lock to ensure that I/O requests are initiated sequentially.  The IRQL is either DISPATCH_LEVEL (full-duplex mode) or DIRQL (half-duplex mode).</p>

<p>When handling I/O in  half-duplex mode, the <b>HwStorStartIo</b> routine does not have to acquire its own spin lock. Also, memory allocation using <a href="https://msdn.microsoft.com/library/windows/hardware/ff567031">StorPortAllocatePool</a> and mutual exclusion via <a href="https://msdn.microsoft.com/library/windows/hardware/ff567025">StorPortAcquireSpinLock</a> are not allowed in the <b>HwStorStartIo</b> routine. In full-duplex mode, <b>StorPortAllocatePool</b> and <b>StorPortAcquireSpinLock</b> may be used in the <b>HwStorStartIo</b> routine.</p>

<p>If a non-virtual miniport supports the concurrent channels optimization (STOR_PERF_CONCURRENT_CHANNELS set by <a href="https://msdn.microsoft.com/library/windows/hardware/ff567114">StorPortInitializePerfOpts</a>), multiple calls to <b>HwStorStartIo</b> concurrently are possible. In this case, the miniport will need to ensure that any shared resources are protected by a lock. With this performance optimization, Storport will not acquire the StartIo lock prior to calling <b>HwStorStartIo</b> and the miniport must provide its own lock if required.</p>

<p>For <a href="NULL">storage virtual miniport drivers</a>, Storport calls <b>HwStorStartIo</b> at any IRQL &lt;= DISPATCH_LEVEL and does not use an internal spin lock. The <b>HwStorStartIo</b> routine may acquire its own spin lock by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff567025">StorPortAcquireSpinLock</a>. Also, calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567031">StorPortAllocatePool</a>  are allowed in the <b>HwStorStartIo</b> routine of a storage virtual miniport driver.</p>

<p>The SRB is expected to be completed when SCSI status is received. When the Storport driver completes the SRB by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff567433">StorPortNotification</a> with a <i>NotificationType</i> of <a href="storage.storportnotification__notificationtype___requestcomplete_">RequestComplete</a>, an SRB is expected to return one of the following values in the <b>SrbStatus</b> field of the Srb:</p>

<p>SRB_STATUS_SUCCESS</p>

<p>The Srb was sent and SCSI status (possibly with data) was returned.</p>

<p>Returns the data and status to the caller.</p>

<p>None, except to complete the request by using  <a href="https://msdn.microsoft.com/library/windows/hardware/ff567446">StorPortNotification for RequestComplete</a>,  probably from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557383">HwStorDpcRoutine</a>.</p>

<p>SRB_STATUS_BUSY</p>

<p>There is a temporary problem with sending the Srb (for example, adapter registers or buffers are busy).</p>

<p>Discards the original Srb and issues a new Srb, including calls to <b>HwStorBuildIo</b> and <b>HwStorStartIo</b>. All data in the SrbExtension will be lost.</p>

<p>Because a new SRB is issued, the miniport must make sure that it never issues SRB_STATUS_BUSY in the middle of a SCSI transaction. After the transaction is started, it must be completed or canceled.  Hardware busy states during the transaction must be handled by the miniport driver.</p>

<p> </p>

<p>The name <b>HwStorStartIo</b> is a placeholder to describe the miniport routine set in the <b>HwStartIo</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559682">HW_INITIALIZATION_DATA</a> structure. This structure is passed in the <i>HwInitializationData</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The actual prototype of this routine is defined in Storport.h as follows:</p>

<p>Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/hh451474">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.</p>

<p>To define a <b>HwStorStartIo</b> callback routine, you must first provide a function declaration that <a href="NULL">Static Driver Verifier</a> (SDV) and other verification tools require, as shown in the following code example:</p>

<p>To define an <b>HwStorStartIo</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.</p>

<p> For example, to define a <b>HwStorStartIo</b> callback routine that is named <i>MyHwStartIo</i>, use the <b>HW_STARTIO</b> type as shown in this code example:</p>

<p>Then, implement your callback routine as follows:</p>

<p>The <b>HW_STARTIO</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_STARTIO</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.</p>

<p><b>HwStorStartIo</b> initiates an I/O operation. StorPort is designed to use miniport private data that is prepared in <a href="https://msdn.microsoft.com/library/windows/hardware/ff557369">HwStorBuildIo</a> and stored in either the <i>DeviceExtension</i> or <i>Srb-&gt;SrbExtension</i>.  Because <b>HwStorBuildIo</b> is called without spin locks, the best driver performance is achieved by preparing as much data  as possible in <b>HwStorBuildIo</b>.</p>

<p>Storport calls <b>HwStorStartIo</b> in the following ways:</p>

<p>For <a href="storage.storage_miniport_drivers">storage non-virtual miniport drivers</a>, depending on the value of <b>SynchronizationModel</b> set in <a href="https://msdn.microsoft.com/library/windows/hardware/ff567785">PORT_CONFIGURATION_INFORMATION</a>, Storport always calls <b>HwStorStartIo</b> the same IRQL and uses an internal spin lock to ensure that I/O requests are initiated sequentially.  The IRQL is either DISPATCH_LEVEL (full-duplex mode) or DIRQL (half-duplex mode).</p>

<p>When handling I/O in  half-duplex mode, the <b>HwStorStartIo</b> routine does not have to acquire its own spin lock. Also, memory allocation using <a href="https://msdn.microsoft.com/library/windows/hardware/ff567031">StorPortAllocatePool</a> and mutual exclusion via <a href="https://msdn.microsoft.com/library/windows/hardware/ff567025">StorPortAcquireSpinLock</a> are not allowed in the <b>HwStorStartIo</b> routine. In full-duplex mode, <b>StorPortAllocatePool</b> and <b>StorPortAcquireSpinLock</b> may be used in the <b>HwStorStartIo</b> routine.</p>

<p>If a non-virtual miniport supports the concurrent channels optimization (STOR_PERF_CONCURRENT_CHANNELS set by <a href="https://msdn.microsoft.com/library/windows/hardware/ff567114">StorPortInitializePerfOpts</a>), multiple calls to <b>HwStorStartIo</b> concurrently are possible. In this case, the miniport will need to ensure that any shared resources are protected by a lock. With this performance optimization, Storport will not acquire the StartIo lock prior to calling <b>HwStorStartIo</b> and the miniport must provide its own lock if required.</p>

<p>For <a href="NULL">storage virtual miniport drivers</a>, Storport calls <b>HwStorStartIo</b> at any IRQL &lt;= DISPATCH_LEVEL and does not use an internal spin lock. The <b>HwStorStartIo</b> routine may acquire its own spin lock by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff567025">StorPortAcquireSpinLock</a>. Also, calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567031">StorPortAllocatePool</a>  are allowed in the <b>HwStorStartIo</b> routine of a storage virtual miniport driver.</p>

<p>The SRB is expected to be completed when SCSI status is received. When the Storport driver completes the SRB by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff567433">StorPortNotification</a> with a <i>NotificationType</i> of <a href="storage.storportnotification__notificationtype___requestcomplete_">RequestComplete</a>, an SRB is expected to return one of the following values in the <b>SrbStatus</b> field of the Srb:</p>

<p>SRB_STATUS_SUCCESS</p>

<p>The Srb was sent and SCSI status (possibly with data) was returned.</p>

<p>Returns the data and status to the caller.</p>

<p>None, except to complete the request by using  <a href="https://msdn.microsoft.com/library/windows/hardware/ff567446">StorPortNotification for RequestComplete</a>,  probably from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557383">HwStorDpcRoutine</a>.</p>

<p>SRB_STATUS_BUSY</p>

<p>There is a temporary problem with sending the Srb (for example, adapter registers or buffers are busy).</p>

<p>Discards the original Srb and issues a new Srb, including calls to <b>HwStorBuildIo</b> and <b>HwStorStartIo</b>. All data in the SrbExtension will be lost.</p>

<p>Because a new SRB is issued, the miniport must make sure that it never issues SRB_STATUS_BUSY in the middle of a SCSI transaction. After the transaction is started, it must be completed or canceled.  Hardware busy states during the transaction must be handled by the miniport driver.</p>

<p> </p>

<p>The name <b>HwStorStartIo</b> is a placeholder to describe the miniport routine set in the <b>HwStartIo</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559682">HW_INITIALIZATION_DATA</a> structure. This structure is passed in the <i>HwInitializationData</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The actual prototype of this routine is defined in Storport.h as follows:</p>

<p>Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/hh451474">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.</p>

<p>To define a <b>HwStorStartIo</b> callback routine, you must first provide a function declaration that <a href="NULL">Static Driver Verifier</a> (SDV) and other verification tools require, as shown in the following code example:</p>

<p>To define an <b>HwStorStartIo</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.</p>

<p> For example, to define a <b>HwStorStartIo</b> callback routine that is named <i>MyHwStartIo</i>, use the <b>HW_STARTIO</b> type as shown in this code example:</p>

<p>Then, implement your callback routine as follows:</p>

<p>The <b>HW_STARTIO</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_STARTIO</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.</p>

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
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>DISPATCH_LEVEL (See Remarks section.)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557369">HwStorBuildIo</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451474">STORAGE_REQUEST_BLOCK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HwStorStartIo routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
