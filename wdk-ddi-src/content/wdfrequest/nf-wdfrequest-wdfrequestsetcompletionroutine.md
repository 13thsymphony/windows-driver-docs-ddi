---
UID: NF:wdfrequest.WdfRequestSetCompletionRoutine
title: WdfRequestSetCompletionRoutine function
author: windows-driver-content
description: The WdfRequestSetCompletionRoutine method registers or deregisters a completion routine for the specified framework request object.
old-location: wdf\wdfrequestsetcompletionroutine.htm
old-project: wdf
ms.assetid: c60f3dd5-2a74-4d7c-8804-35b9dd91dce4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_4dea9104-1bfd-4add-b991-f02d57f840cb.xml, WdfRequestSetCompletionRoutine, WdfRequestSetCompletionRoutine method, kmdf.wdfrequestsetcompletionroutine, wdf.wdfrequestsetcompletionroutine, wdfrequest/WdfRequestSetCompletionRoutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, ReqCompletionRoutine
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfRequestSetCompletionRoutine
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WdfRequestSetCompletionRoutine function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestSetCompletionRoutine</b> method registers or deregisters a completion routine for the specified framework request object.

## Syntax

```
void WdfRequestSetCompletionRoutine(
  WDFREQUEST                         Request,
  PFN_WDF_REQUEST_COMPLETION_ROUTINE CompletionRoutine,
  __drv_aliasesMem WDFCONTEXT        CompletionContext
);
```

## Parameters

`Request`

A handle to a framework request object.

`CompletionRoutine`

A pointer to a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function, if the driver is registering a completion routine, or <b>NULL</b> of the driver is deregistering a previously registered completion routine.

`CompletionContext`

An untyped pointer to driver-defined context information that the framework passes to the <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function. This parameter is optional and can be <b>NULL</b>.


## Return Value

None.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

If your driver forwards I/O requests, but if you want your driver to be notified when a lower-level driver completes the request, your driver can provide a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function and call <b>WdfRequestSetCompletionRoutine</b> to register the function. The framework calls the callback function after a lower-level driver completes the I/O request. 

For more information about <b>WdfRequestSetCompletionRoutine</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.


#### Examples

For a code example that uses <b>WdfRequestSetCompletionRoutine</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfrequest.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, ReqCompletionRoutine |

## See Also

<a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a>