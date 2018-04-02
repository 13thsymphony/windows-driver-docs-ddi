---
UID: NF:wdfrequest.WdfRequestWdmFormatUsingStackLocation
title: WdfRequestWdmFormatUsingStackLocation function
author: windows-driver-content
description: The WdfRequestWdmFormatUsingStackLocation method formats an I/O request by copying the contents of a specified WDM I/O stack location structure to the next stack location in the request.
old-location: wdf\wdfrequestwdmformatusingstacklocation.htm
old-project: wdf
ms.assetid: 9ee3d748-f9aa-43d6-b472-7b55d2034fc7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_a210a31a-e3a5-4bbd-af19-5be5f7651757.xml, WdfRequestWdmFormatUsingStackLocation, WdfRequestWdmFormatUsingStackLocation method, kmdf.wdfrequestwdmformatusingstacklocation, wdf.wdfrequestwdmformatusingstacklocation, wdfrequest/WdfRequestWdmFormatUsingStackLocation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, RequestFormattedValid
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
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
api_name:
-	WdfRequestWdmFormatUsingStackLocation
product:
- Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WdfRequestWdmFormatUsingStackLocation function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfRequestWdmFormatUsingStackLocation</b> method formats an I/O request by copying the contents of a specified WDM <a href="https://msdn.microsoft.com/62c8ee00-c7cb-4aa1-90ab-b8bedbd818ee">I/O stack location</a> structure to the next stack location in the request.

## Syntax

```
void WdfRequestWdmFormatUsingStackLocation(
  WDFREQUEST         Request,
  PIO_STACK_LOCATION Stack
);
```

## Parameters

`Request`

A handle to a framework request object.

`Stack`

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a> structure that contains driver-supplied information.


## Return Value

None.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

The <b>WdfRequestWdmFormatUsingStackLocation</b> method copies the information that is supplied by the <i>Stack</i> parameter into the next IRP stack location in the request. 

<b>WdfRequestWdmFormatUsingStackLocation</b> formats the request independent of whether the I/O target object of the request is local or remote.

If you want to set a completion routine for the request, your driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550030">WdfRequestSetCompletionRoutine</a> after calling <b>WdfRequestWdmFormatUsingStackLocation</b>.

For more information about <b>WdfRequestWdmFormatUsingStackLocation</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.


#### Examples

The following code example supplies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a> structure for an I/O request, sets a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function, and then sends the request to an I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IO_STACK_LOCATION  ioStackLocation;
BOOLEAN sendStatus;
...
//
// Initialize the IO_STACK_LOCATION structure here.
//
...
//
// Assign the IO_STACK_LOCATION structure to the request.
//
WdfRequestWdmFormatUsingStackLocation(
                                      request,
                                      &amp;ioStackLocation
                                      );
//
// Assign a CompletionRoutine callback function.
//
WdfRequestSetCompletionRoutine(
                               Request,
                               RequestTimeoutComplete,
                               NULL
                               );
//
// Send the request.
//
sendStatus = WdfRequestSend(
                            Request,
                            target,
                            NULL
                            );</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfrequest.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, RequestFormattedValid |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550030">WdfRequestSetCompletionRoutine</a>