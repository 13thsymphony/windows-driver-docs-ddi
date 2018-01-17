---
UID: NF:wdfdmatransaction.WdfDmaTransactionStopSystemTransfer
title: WdfDmaTransactionStopSystemTransfer function
author: windows-driver-content
description: The WdfDmaTransactionStopSystemTransfer method attempts to stop a system-mode DMA transfer after the framework has called EvtProgramDma.
old-location: wdf\wdfdmatransactionstopsystemtransfer.htm
old-project: wdf
ms.assetid: 55674946-A2DA-4695-8673-6BF3123FB5FC
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDmaTransactionStopSystemTransfer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.alt-api: WdfDmaTransactionStopSystemTransfer
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
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product: Windows 10 or later.
---

# WdfDmaTransactionStopSystemTransfer function



## -description
<p class="CCE_Message">[Applies to KMDF only]


   The 
  <b>WdfDmaTransactionStopSystemTransfer</b> method attempts to stop a system-mode DMA transfer after the framework has called <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a>.



## -syntax

````
void WdfDmaTransactionStopSystemTransfer(
  _In_ WDFDMATRANSACTION DmaTransaction
);
````


## -parameters

### -param DmaTransaction [in]

A handle to an initialized DMA transaction object.


## -returns
This method does not return a value.


## -remarks
Only a driver that uses system-mode DMA should call  <b>WdfDmaTransactionStopSystemTransfer</b>.

A driver using bus-mastering  DMA is responsible for programming its own dedicated DMA controller. In the event of a request cancellation, timeout, or device error, the driver can program the DMA controller to stop transferring data.

In contrast, a driver using system-mode DMA must rely on the hardware abstraction layer (HAL) to program the shared DMA controller.  When a driver calls <b>WdfDmaTransactionStopSystemTransfer</b>, the framework notifies the HAL that the transfer must be stopped and returns immediately.

The framework next calls the driver's <a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete.md">EvtDmaTransactionDmaTransferComplete</a> callback function, if the driver has provided one.  If not, the framework returns FALSE when the driver next calls <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompleted.md">WdfDmaTransactionDmaCompleted</a>.

If your driver calls this method on an operating system earlier than Windows 8, <a href="wdf.using_kmdf_verifier">the framework's verifier</a> reports an error.

 For more information about system-mode DMA, see <a href="https://msdn.microsoft.com/CCC77C15-69CA-44CB-8DEB-29F3EAEA44F6">Supporting System-Mode DMA</a>.

 For more information about canceling DMA transactions, see <a href="https://msdn.microsoft.com/1E1D659D-80C9-45B1-B96F-78E5A1EE4F6B">Canceling DMA Transactions</a>.

The following code example shows how a driver might call <b>WdfDmaTransactionStopSystemTransfer</b> from an <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> event callback function that it registers to be called if an I/O request times out.

The following code example shows how a driver might call <b>WdfDmaTransactionStopSystemTransfer</b> from an <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function. The driver previously called <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a> from its I/O request handler to register the callback.


## -see-also
<dl>
<dt>
<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncancel.md">WdfDmaTransactionCancel</a>
</dt>
<dt>
<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionStopSystemTransfer method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

