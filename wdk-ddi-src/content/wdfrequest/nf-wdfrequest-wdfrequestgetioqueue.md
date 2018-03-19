---
UID: NF:wdfrequest.WdfRequestGetIoQueue
title: WdfRequestGetIoQueue function
author: windows-driver-content
description: The WdfRequestGetIoQueue method returns a handle to the framework queue object from which a specified I/O request was delivered.
old-location: wdf\wdfrequestgetioqueue.htm
old-project: wdf
ms.assetid: 9b7d67a3-2899-47b1-9652-d3696d37ec2d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_5ac140be-04cf-480c-a917-9942d23b550f.xml, WdfRequestGetIoQueue, WdfRequestGetIoQueue method, kmdf.wdfrequestgetioqueue, wdf.wdfrequestgetioqueue, wdfrequest/WdfRequestGetIoQueue
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
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
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
-	WdfRequestGetIoQueue
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WdfRequestGetIoQueue function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestGetIoQueue</b> method returns a handle to the framework queue object from which a specified I/O request was delivered.

## Syntax

````
WDFQUEUE WdfRequestGetIoQueue(
  _In_ WDFREQUEST Request
);
````

## Parameters

`Request`

A handle to a framework request object.


## Return Value

<b>WdfRequestGetIoQueue</b> returns a handle to a framework queue object. If the request was created by the driver, or if the driver has already completed the specified I/O request, the method returns <b>NULL</b>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information about <b>WdfRequestGetIoQueue</b>, see <a href="https://msdn.microsoft.com/a686ea00-6987-480a-a4ce-892e1efbed87">Obtaining Information About an I/O Request</a>.


#### Examples

The following code example obtains a handle to the device object that represents the device that a request belongs to.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFDEVICE  device;

device = WdfIoQueueGetDevice(WdfRequestGetIoQueue(Request));</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfrequest.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfio\nf-wdfio-wdfioqueuegetdevice.md">WdfIoQueueGetDevice</a>