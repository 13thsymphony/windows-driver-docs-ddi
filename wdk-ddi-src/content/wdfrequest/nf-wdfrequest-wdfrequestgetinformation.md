---
UID: NF:wdfrequest.WdfRequestGetInformation
title: WdfRequestGetInformation function
author: windows-driver-content
description: The WdfRequestGetInformation method returns completion status information for a specified I/O request.
old-location: wdf\wdfrequestgetinformation.htm
old-project: wdf
ms.assetid: fd5f29f7-e9c6-48c4-8704-5db37b8c6337
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdfrequest/WdfRequestGetInformation, wdf.wdfrequestgetinformation, WdfRequestGetInformation, WdfRequestGetInformation method, DFRequestObjectRef_ea947de9-aea4-4e66-8686-f4ca5a1385c4.xml, kmdf.wdfrequestgetinformation
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfRequestGetInformation
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WdfRequestGetInformation function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestGetInformation</b> method returns completion status information for a specified I/O request.

## Syntax

````
ULONG_PTR WdfRequestGetInformation(
  _In_ WDFREQUEST Request
);
````

## Parameters

`Request`

A handle to a framework request object.


## Return Value

<b>WdfRequestGetInformation</b> returns the information that a lower-level driver set by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetinformation.md">WdfRequestSetInformation</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

A driver can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetinformation.md">WdfRequestSetInformation</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a> to set completion status information for an I/O request. Your driver can call <b>WdfRequestGetInformation</b> after a lower-level driver completes a request, to obtain completion status information that the lower-level driver set. 

If your driver calls <b>WdfRequestGetInformation</b> after it calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> to complete the request, <b>WdfRequestGetInformation</b> returns <b>NULL</b>.

For more information about <b>WdfRequestGetInformation</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.


#### Examples

The following code example sends an I/O request to an I/O target and then obtains status information that the I/O target provided.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>ULONG_PTR  informationRetrieved = NULL;

status = WdfIoTargetSendWriteSynchronously(
                                           ioTarget,
                                           request,
                                           &amp;outputMemoryDescriptor,
                                           NULL,
                                           NULL,
                                           &amp;bytesWritten
                                           );
if (NT_SUCCESS(status)) {
    informationRetrieved = WdfRequestGetInformation(request);
}</pre>
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

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetinformation.md">WdfRequestSetInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestGetInformation method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>