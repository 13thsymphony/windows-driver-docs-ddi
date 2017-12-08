---
UID: NF.wdfdmatransaction.WdfDmaTransactionAllocateResources
title: WdfDmaTransactionAllocateResources function
author: windows-driver-content
description: The WdfDmaTransactionAllocateResources method reserves a single-packet or system-mode DMA enabler for exclusive (and repeated) use with the specified transaction object.
old-location: wdf\wdfdmatransactionallocateresources.htm
old-project: wdf
ms.assetid: 69D251D9-1B33-49FD-8D48-EFCBD6640632
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfDmaTransactionAllocateResources
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.alt-api: WdfDmaTransactionAllocateResources
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfDmaTransactionAllocateResources function



## -description
<p class="CCE_Message">[Applies to KMDF only]

   The <b>WdfDmaTransactionAllocateResources</b> method reserves a single-packet or system-mode DMA enabler for exclusive (and repeated) use with the specified transaction object. The driver can initialize and initiate the transaction multiple times while holding reserved resources.


## -syntax

````
NTSTATUS WdfDmaTransactionAllocateResources(
  _In_ WDFDMATRANSACTION   DmaTransaction,
  _In_ WDF_DMA_DIRECTION   DmaDirection,
  _In_ ULONG               RequiredMapRegisters,
  _In_ PFN_WDF_RESERVE_DMA EvtReserveDmaFunction,
  _In_ PVOID               EvtReserveDmaContext
);
````


## -parameters

### -param DmaTransaction [in]

A handle to the DMA transaction object for which DMA resources should be reserved.

### -param DmaDirection [in]

A <a href="wdf.wdf_dma_direction">WDF_DMA_DIRECTION</a>-typed value specifying the DMA transfer direction for which the resources are being reserved. If the driver did not specify a duplex profile, the framework ignores this value.

### -param RequiredMapRegisters [in]

The number of map registers the driver wants to reserve. If zero, the framework derives the required number of map registers from the initialized transaction.

### -param EvtReserveDmaFunction [in]

A pointer to the driver's <a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_reserve_dma.md">EvtReserveDma</a> event callback function.

### -param EvtReserveDmaContext [in]

A pointer to a buffer containing the context to be provided to the driver's <a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_reserve_dma.md">EvtReserveDma</a> event callback function.

## -returns
<b>WdfDmaTransactionAllocateResources</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method returns one of the following values.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>DmaDirection</i> parameter contains an invalid value.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The number of map register requests exceeds the number assigned to the enabler, or the driver previously called <a href="wdf.wdfdmatransactionsetimmediateexecution">WdfDmaTransactionSetImmediateExecution</a> and the resources needed for the request are unavailable.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>DMA version 3 or later is not enabled, or the driver called this method for a scatter-gather DMA enabler.

 

## -remarks
<b>WdfDmaTransactionAllocateResources</b> sends a request for map registers to the system DMA engine.  When the request has been fulfilled, the framework calls the driver's <a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_reserve_dma.md">EvtReserveDma</a> event callback function. For more information about reserving resources, see <a href="wdf.reserving_dma_resources">Reserving DMA Resources</a>.

Framework-based drivers typically call <b>WdfDmaTransactionAllocateResources</b> from within an <a href="wdf.request_handlers">I/O request handler</a>.  A driver can also call <b>WdfDmaTransactionAllocateResources</b> from its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function, after creating a DMA enabler object.

  When called with a scatter/gather DMA enabler, <b>WdfDmaTransactionAllocateResources</b> causes a verifier bug check.

The driver must create the transaction specified by <i>DmaTransaction</i> prior to calling <b>WdfDmaTransactionAllocateResources</b>. After calling <b>WdfDmaTransactionAllocateResources</b>, the driver initializes and initiates the transaction. The driver can reinitialize and reinitiate the same transaction object multiple times, avoiding the delay that would otherwise occur between transactions as map registers were freed back to the HAL and then reallocated.

A driver could call <b>WdfDmaTransactionAllocateResources</b> in the following situations:

Before calling <b>WdfDmaTransactionAllocateResources</b>, the driver must determine the number of map registers needed for any transaction that it will initiate using this reservation. To do so, the driver can call either the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540562">ADDRESS_AND_SIZE_TO_SPAN_PAGES</a> macro or <a href="wdf.wdfdmatransactiongettransferinfo">WdfDmaTransactionGetTransferInfo</a>.

 When calling <b>WdfDmaTransactionAllocateResources</b>, the driver should not request more map registers than it requested when it created the enabler.

To call <b>WdfDmaTransactionAllocateResources</b> in a non-blocking manner, the driver should first call <a href="wdf.wdfdmatransactionsetimmediateexecution">WdfDmaTransactionSetImmediateExecution</a>.

<b>WdfDmaTransactionAllocateResources</b> requires DMA version 3.
 To select DMA version 3, set the <b>WdmDmaVersionOverride</b> member of <a href="wdf.wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> to 3.


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
Minimum KMDF version
</th>
<td width="70%">
1.11
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfdmatransaction.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;=DISPATCH_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfdmatransactioncreate">WdfDmaTransactionCreate</a>
</dt>
<dt>
<a href="wdf.wdfdmatransactionexecute">WdfDmaTransactionExecute</a>
</dt>
<dt>
<a href="wdf.wdfdmatransactionfreeresources">WdfDmaTransactionFreeResources</a>
</dt>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a>
</dt>
<dt>
<a href="wdf.wdfdmaenablercreate">WdfDmaEnablerCreate</a>
</dt>
<dt>
<a href="wdf.wdfdmatransactionsetimmediateexecution">WdfDmaTransactionSetImmediateExecution</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionAllocateResources method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
