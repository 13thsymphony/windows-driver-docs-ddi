---
UID: NF:ndis.NdisMQueueDpc
title: NdisMQueueDpc function
author: windows-driver-content
description: NDIS miniport drivers call the NdisMQueueDpc function to schedule DPC calls on CPUs.
old-location: netvista\ndismqueuedpc.htm
old-project: netvista
ms.assetid: 203be18a-b3c5-420b-bcd1-1134beb1c8bd
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMQueueDpc, NdisMQueueDpc function [Network Drivers Starting with Windows Vista], ndis/NdisMQueueDpc, ndis_interrupts_functions_ref_a4b04210-b671-4ab3-8b5b-989bed907aed.xml, netvista.ndismqueuedpc
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMQueueDpc
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMQueueDpc function
NDIS miniport drivers call the 
  <b>NdisMQueueDpc</b> function to schedule DPC calls on CPUs.

## Syntax

````
ULONG NdisMQueueDpc(
  _In_     NDIS_HANDLE NdisInterruptHandle,
  _In_     ULONG       MessageId,
  _In_     ULONG       TargetProcessors,
  _In_opt_ PVOID       MiniportDpcContext
);
````

## Parameters

`NdisInterruptHandle`

An interrupt handle that the miniport driver obtained in a previous call to the 
     <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">
     NdisMRegisterInterruptEx</a> function.

`MessageId`

An MSI message ID for the DPC. If the DPC is for a line-based interrupt, this parameter is not
     used and it should be set to zero. Otherwise, 
     <i>MessageId</i> is an index to the 
     <a href="..\wdm\ns-wdm-_io_interrupt_message_info_entry.md">
     IO_INTERRUPT_MESSAGE_INFO_ENTRY</a> structures inside a 
     <a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">
     IO_INTERRUPT_MESSAGE_INFO</a> structure. NDIS passes a pointer to the associated
     IO_INTERRUPT_MESSAGE_INFO structure at the 
     <b>MessageInfoTable</b> member when the driver successfully registers for MSI with the 
     <b>NdisMRegisterInterruptEx</b> function.

`TargetProcessors`

A bitmap that indicates the target processors for which NDIS should schedule a DPC. Each bit in 
     <i>TargetProcessors</i> identifies a CPU. If the caller sets bit 0, NDIS schedules a DPC for CPU 0. If the caller sets bit 1, NDIS
     schedules a DPC for CPU 1, and so forth.

`MiniportDpcContext`

A pointer to a caller-specified context area. NDIS passes this pointer to the 
     <i>MiniportDpcContext</i> parameter of the 
     <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a> and 
     <a href="..\ndis\nc-ndis-miniport_message_interrupt_dpc.md">
     MiniportMessageInterruptDPC</a> functions.


## Return Value

<b>NdisMQueueDpc</b> returns a bitmap that indicates the target processors for which NDIS successfully
      scheduled a DPC. Each bit in the return value identifies a CPU. If NDIS sets bit 0, NDIS scheduled a DPC for CPU 0. If NDIS sets bit 1, NDIS scheduled a DPC
      for CPU 1, and so forth.

If the driver requested a DPC for a CPU, and NDIS indicates that it did not schedule that DPC, the
      DPC was not scheduled because a DPC was already scheduled for that CPU.

## Remarks

NDIS calls 
    <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a> or 
    <a href="..\ndis\nc-ndis-miniport_message_interrupt_dpc.md">
    MiniportMessageInterruptDPC</a> to complete the deferred processing of an interrupt. The miniport
    driver can call 
    <b>NdisMQueueDpc</b> to request additional DPC calls for other processors.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use NdisMQueueDpcEx.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | Any level |

## See Also

<a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a>



<a href="..\ndis\nc-ndis-miniport_message_interrupt_dpc.md">MiniportMessageInterruptDPC</a>



<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>



<a href="..\ndis\nf-ndis-ndismqueuedpcex.md">NdisMQueueDpcEx</a>