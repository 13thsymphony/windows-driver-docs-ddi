---
UID: NF:wdfrequest.WdfRequestSetInformation
title: WdfRequestSetInformation function
author: windows-driver-content
description: The WdfRequestSetInformation method sets completion status information for a specified I/O request.
old-location: wdf\wdfrequestsetinformation.htm
old-project: wdf
ms.assetid: 2a5cccb3-24aa-404a-b887-2ccbe98a0673
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfRequestSetInformation
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
req.alt-api: WdfRequestSetInformation
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestSetInformation function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestSetInformation</b> method sets completion status information for a specified I/O request.



## -syntax

````
VOID WdfRequestSetInformation(
  _In_ WDFREQUEST Request,
  _In_ ULONG_PTR  Information
);
````


## -parameters

### -param Request [in]

A handle to a framework request object.


### -param Information [in]

Driver-defined completion status information for the request.


## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
Framework-based drivers use the <b>WdfRequestSetInformation</b> method to supply driver-specific information that is associated with the completion of an I/O request, such as the number of bytes transferred. Other drivers can obtain this information by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetinformation.md">WdfRequestGetInformation</a>. 

Drivers can also specify completion status information by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a>.

For more information about <b>WdfRequestSetInformation</b>, see <a href="https://msdn.microsoft.com/ec5aef7a-110e-430c-902d-669ccc7095ac">Completing I/O Requests</a>.

The following code example sets request completion information that is based on the value of the I/O control code that an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_device_control.md">EvtIoDeviceControl</a> callback function receives.


## -see-also
<dl>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetinformation.md">WdfRequestGetInformation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestSetInformation method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

