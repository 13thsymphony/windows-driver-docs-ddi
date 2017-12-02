---
UID: NF.wdm.KeSetImportanceDpc
title: KeSetImportanceDpc
author: windows-driver-content
description: The KeSetImportanceDpc routine specifies how soon the DPC routine is run.
old-location: kernel\kesetimportancedpc.htm
old-project: kernel
ms.assetid: 0feb053b-6b58-4b26-8549-a6cf3996a3e6
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KeSetImportanceDpc
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
req.alt-api: KeSetImportanceDpc
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
req.iface: 
req.product: Windows 10 or later.
---

# KeSetImportanceDpc function



## -description
<p>The <b>KeSetImportanceDpc</b> routine specifies how soon the DPC routine is run. </p>


## -syntax

````
VOID KeSetImportanceDpc(
  _Inout_ PRKDPC          Dpc,
  _In_    KDPC_IMPORTANCE Importance
);
````


## -parameters
<dl>

### -param Dpc [in, out]

<dd>
<p>Pointer to the caller's DPC object, which <a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a> already initialized. </p>
</dd>

### -param Importance [in]

<dd>
<p>Specifies one of the following system-defined values to determine the behavior of <a href="..\wdm\nf-wdm-keinsertqueuedpc.md">KeInsertQueueDpc</a> and <a href="..\wdm\nf-wdm-iorequestdpc.md">IoRequestDpc</a> when either routine is used to queue the DPC.</p>
<p></p>
<dl>

### -param LowImportance

<dd>
<p>Place the DPC at the end of the DPC queue, and do not begin processing of the queue. </p>
</dd>

### -param MediumImportance

<dd>
<p>Place the DPC at the end of the DPC queue. If the DPC is assigned to the current processor's DPC queue, begin processing the queue immediately. <b>MediumImportance</b> is the default value for <i>Importance</i>. </p>
</dd>

### -param MediumHighImportance

<dd>
<p>Place the DPC at the end of the DPC queue, and begin processing the queue immediately. MediumHighImportance is available only on Windows Vista and later versions of Windows.</p>
</dd>

### -param HighImportance

<dd>
<p>Place the DPC at the beginning of the DPC queue, and begin processing the queue immediately. </p>
</dd>
</dl>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The <b>KeSetImportanceDpc</b> routine influences how soon a DPC is run after it is queued by determining:</p>

<p>The location of the DPC within the DPC queue. Typically, the <b>KeInsertQueueDpc</b> and <b>IoRequestDpc</b> routines place a DPC at the end of the queue. If a driver first calls <b>KeSetImportanceDpc</b> with <i>Importance</i> = <b>HighImportance</b>, <b>KeInsertQueueDpc</b> and <b>IoRequestDpc</b> will place the DPC at the beginning of the queue.</p>

<p>When the system begins processing the DPC queue. Typically, <b>KeInsertQueueDpc</b> and <b>IoRequestDpc</b> immediately begin processing the DPC queue for the current processor. Drivers can specify different values for <i>Importance</i> to change this behavior.</p>

<p>By default, DPCs are assigned to the DPC queue for the current processor, so specifying <b>MediumImportance</b> or <b>MediumHighImportance</b> for <i>Importance</i> has the same effect. However, drivers can use <a href="..\wdm\nf-wdm-kesettargetprocessordpc.md">KeSetTargetProcessorDpc</a> to change the processor that the DPC will be assigned to.</p>

<p>For Windows Vista and later versions of the Windows operating system, you can use <b>KeSetImportanceDpc</b> for threaded DPCs. If the caller sets <i>Importance</i> to <b>HighImportance</b>, the DPC is placed at the beginning of the queue; otherwise, it is placed at the end. The routine does not affect when the threaded DPC queue is processed. Threaded DPCs are always processed by a dedicated thread at IRQL = PASSIVE_LEVEL. For more information about threaded DPCs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564621">Threaded DPCs</a>.</p>

<p>Note that a driver must call <b>KeSetImportanceDpc</b> before it calls <b>KeInsertQueueDpc</b> and <b>IoRequestDpc</b> to have any effect.</p>

<p>For more information about how the system processes the DPC queue, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558754">Organization of DPC Queues</a>.</p>

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
<p>Available starting with Windows 2000.</p>
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
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-iorequestdpc.md">IoRequestDpc</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keinsertqueuedpc.md">KeInsertQueueDpc</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kesettargetprocessordpc.md">KeSetTargetProcessorDpc</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kesynchronizeexecution.md">KeSynchronizeExecution</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeSetImportanceDpc routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
