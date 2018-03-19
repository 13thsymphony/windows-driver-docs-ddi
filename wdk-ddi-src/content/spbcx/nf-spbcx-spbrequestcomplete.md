---
UID: NF:spbcx.SpbRequestComplete
title: SpbRequestComplete function
author: windows-driver-content
description: The SpbRequestComplete method completes an I/O request and supplies a completion status.
old-location: spb\spbrequestcomplete.htm
old-project: SPB
ms.assetid: 356BC81E-8FE9-4BC7-83E5-20A64D149A0D
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SPB.spbrequestcomplete, SpbRequestComplete, SpbRequestComplete method [Buses], spbcx/SpbRequestComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: spbcx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Spbcxstubs.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	spbcxstubs.lib
-	spbcxstubs.dll
api_name:
-	SpbRequestComplete
product: Windows
targetos: Windows
req.typenames: SPB_REQUEST_TYPE, *PSPB_REQUEST_TYPE
req.product: Windows 10 or later.
---


# SpbRequestComplete function
The <b>SpbRequestComplete</b> method completes an I/O request and supplies a completion status.

## Syntax

````
VOID SpbRequestComplete(
  _In_ SPBREQUEST Request,
  _In_ NTSTATUS   CompletionStatus
);
````

## Parameters

`Request`

An <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a> handle to the I/O request to complete. The SPB controller driver previously received this handle through one of its registered <a href="https://msdn.microsoft.com/1DA1FF41-FB01-45CC-B0C1-EAF2C81D0CDA">event callback functions</a>.

`CompletionStatus`

An NTSTATUS value that represents the completion status of the request. Valid status values include, but are not limited to, the following:





#### STATUS_SUCCESS

The I/O request completed successfully.



#### STATUS_CANCELLED

The I/O request is canceled.



#### STATUS_UNSUCCESSFUL

The driver encountered an error while processing the I/O request.


## Return Value

None.

## Remarks

Your controller driver calls this method to complete an I/O request that it previously received during one of the following callbacks:

<a href="https://msdn.microsoft.com/5A4BC061-4703-4C46-BD5D-A891F3DA8842">EvtSpbControllerIoOther</a>
<a href="https://msdn.microsoft.com/2BC0E6E7-7EE1-487A-9276-AE8EBB3FFD43">EvtSpbControllerIoRead</a>
<a href="https://msdn.microsoft.com/C56F1528-5FDA-4BC9-AB32-7882FB0F7713">EvtSpbControllerIoSequence</a>
<a href="https://msdn.microsoft.com/D97C3A17-309E-4364-8DFB-9073901D332E">EvtSpbControllerIoWrite</a>
Call <b>SpbRequestComplete</b> instead of the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> method to complete I/O requests received by the callback functions in the preceding list.

A bug check occurs if the caller supplies an invalid SPBREQUEST handle.

A call to <b>SpbRequestComplete</b> represents the final stage in the processing of an I/O request. When this method returns, the <i>Request</i> handle value is no longer valid.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.  |
| **Target Platform** | Universal |
| **Header** | spbcx.h |
| **Library** | Spbcxstubs.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/D97C3A17-309E-4364-8DFB-9073901D332E">EvtSpbControllerIoWrite</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a>



<a href="https://msdn.microsoft.com/5A4BC061-4703-4C46-BD5D-A891F3DA8842">EvtSpbControllerIoOther</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>



<a href="https://msdn.microsoft.com/C56F1528-5FDA-4BC9-AB32-7882FB0F7713">EvtSpbControllerIoSequence</a>



<a href="https://msdn.microsoft.com/2BC0E6E7-7EE1-487A-9276-AE8EBB3FFD43">EvtSpbControllerIoRead</a>