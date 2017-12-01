---
UID: NF.ndis.NdisMQueueDpc
title: NdisMQueueDpc
author: windows-driver-content
description: NDIS miniport drivers call the NdisMQueueDpc function to schedule DPC calls on CPUs.
old-location: netvista\ndismqueuedpc.htm
old-project: netvista
ms.assetid: 203be18a-b3c5-420b-bcd1-1134beb1c8bd
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NdisMQueueDpc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use NdisMQueueDpcEx.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMQueueDpc
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
req.iface: 
---

# NdisMQueueDpc function



## -description
<p>NDIS miniport drivers call the 
  <b>NdisMQueueDpc</b> function to schedule DPC calls on CPUs.</p>


## -syntax

````
ULONG NdisMQueueDpc(
  _In_     NDIS_HANDLE NdisInterruptHandle,
  _In_     ULONG       MessageId,
  _In_     ULONG       TargetProcessors,
  _In_opt_ PVOID       MiniportDpcContext
);
````


## -parameters
<dl>

### -param <i>NdisInterruptHandle</i> [in]

<dd>
<p>An interrupt handle that the miniport driver obtained in a previous call to the 
     <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">
     NdisMRegisterInterruptEx</a> function.</p>
</dd>

### -param <i>MessageId</i> [in]

<dd>
<p>An MSI message ID for the DPC. If the DPC is for a line-based interrupt, this parameter is not
     used and it should be set to zero. Otherwise, 
     <i>MessageId</i> is an index to the 
     <a href="..\wdm\ns-wdm--io-interrupt-message-info-entry.md">
     IO_INTERRUPT_MESSAGE_INFO_ENTRY</a> structures inside a 
     <a href="..\wdm\ns-wdm--io-interrupt-message-info.md">
     IO_INTERRUPT_MESSAGE_INFO</a> structure. NDIS passes a pointer to the associated
     IO_INTERRUPT_MESSAGE_INFO structure at the 
     <b>MessageInfoTable</b> member when the driver successfully registers for MSI with the 
     <b>NdisMRegisterInterruptEx</b> function.</p>
</dd>

### -param <i>TargetProcessors</i> [in]

<dd>
<p>A bitmap that indicates the target processors for which NDIS should schedule a DPC. Each bit in 
     <i>TargetProcessors</i> identifies a CPU. If the caller sets bit 0, NDIS schedules a DPC for CPU 0. If the caller sets bit 1, NDIS
     schedules a DPC for CPU 1, and so forth.</p>
</dd>

### -param <i>MiniportDpcContext</i> [in, optional]

<dd>
<p>A pointer to a caller-specified context area. NDIS passes this pointer to the 
     <i>MiniportDpcContext</i> parameter of the 
     <a href="..\ndis\nc-ndis-miniport-interrupt-dpc.md">MiniportInterruptDPC</a> and 
     <a href="..\ndis\nc-ndis-miniport-message-interrupt-dpc.md">
     MiniportMessageInterruptDPC</a> functions.</p>
</dd>
</dl>

## -returns
<p><b>NdisMQueueDpc</b> returns a bitmap that indicates the target processors for which NDIS successfully
      scheduled a DPC. Each bit in the return value identifies a CPU. If NDIS sets bit 0, NDIS scheduled a DPC for CPU 0. If NDIS sets bit 1, NDIS scheduled a DPC
      for CPU 1, and so forth.</p>

<p>If the driver requested a DPC for a CPU, and NDIS indicates that it did not schedule that DPC, the
      DPC was not scheduled because a DPC was already scheduled for that CPU.</p>

## -remarks
<p>NDIS calls 
    <a href="..\ndis\nc-ndis-miniport-interrupt-dpc.md">MiniportInterruptDPC</a> or 
    <a href="..\ndis\nc-ndis-miniport-message-interrupt-dpc.md">
    MiniportMessageInterruptDPC</a> to complete the deferred processing of an interrupt. The miniport
    driver can call 
    <b>NdisMQueueDpc</b> to request additional DPC calls for other processors.</p>

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
<p>Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use <a href="..\ndis\nf-ndis-ndismqueuedpcex.md">NdisMQueueDpcEx</a>.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
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
<a href="..\ndis\nc-ndis-miniport-interrupt-dpc.md">MiniportInterruptDPC</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-message-interrupt-dpc.md">MiniportMessageInterruptDPC</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismqueuedpcex.md">NdisMQueueDpcEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMQueueDpc function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
