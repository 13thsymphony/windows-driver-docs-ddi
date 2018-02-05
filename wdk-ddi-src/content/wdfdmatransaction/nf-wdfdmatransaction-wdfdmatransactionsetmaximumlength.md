---
UID : NF:wdfdmatransaction.WdfDmaTransactionSetMaximumLength
title : WdfDmaTransactionSetMaximumLength function
author : windows-driver-content
description : The WdfDmaTransactionSetMaximumLength method sets the maximum length for the DMA transfers that are associated with a specified DMA transaction.
old-location : wdf\wdfdmatransactionsetmaximumlength.htm
old-project : wdf
ms.assetid : b195c6df-79c4-427d-b722-309f43a4e150
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.wdfdmatransactionsetmaximumlength, DFDmaObjectRef_966c396e-c161-46d6-856e-9bc9aa30c610.xml, PFN_WDFDMATRANSACTIONSETMAXIMUMLENGTH, wdfdmatransaction/WdfDmaTransactionSetMaximumLength, WdfDmaTransactionSetMaximumLength, kmdf.wdfdmatransactionsetmaximumlength, WdfDmaTransactionSetMaximumLength method
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfdmatransaction.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : DriverCreate
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDF_DMA_SYSTEM_PROFILE_CONFIG, WDF_DMA_SYSTEM_PROFILE_CONFIG"
req.product : Windows 10 or later.
---


# WdfDmaTransactionSetMaximumLength function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionSetMaximumLength</b> method sets the maximum length for the DMA transfers that are associated with a specified DMA transaction.

## Syntax

````
VOID WdfDmaTransactionSetMaximumLength(
  _In_ WDFDMATRANSACTION DmaTransaction,
  _In_ size_t            MaximumLength
);
````

## Parameters

`DmaTransaction`

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>.

`MaximumLength`

The maximum size, in bytes, that the device can handle in a single DMA transfer operation. If your driver must run on versions of the Microsoft Windows operating systems that support a maximum of 16 <a href="https://msdn.microsoft.com/library/windows/hardware/ff554406">map registers</a>, <i>MaximumLength</i> must be less than 65536.

The <i>MaximumLength</i> value applies only to the specified DMA transaction, as follows:
<ul>
<li>
If the specified value is less than the default value that the driver specified in its <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a> structure, the specified value overrides the default value. 

</li>
<li>
If the specified value is greater than the default value, the specified value is ignored.

</li>
</ul>


## Return Value

None.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

Your driver  must initialize the DMA transaction before calling <b>WdfDmaTransactionSetMaximumLength</b>.

For information about initializing a DMA transaction, see <a href="https://msdn.microsoft.com/1982c3fa-9e4a-4b26-8902-321223d9159f">Creating and Initializing a DMA Transaction</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfdmatransaction.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate |

## See Also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>

<a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionSetMaximumLength method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>