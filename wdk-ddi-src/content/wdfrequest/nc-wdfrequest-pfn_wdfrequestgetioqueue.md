---
UID: NC:wdfrequest.PFN_WDFREQUESTGETIOQUEUE
title: PFN_WDFREQUESTGETIOQUEUE function
author: windows-driver-content
description: The WdfRequestGetIoQueue method returns a handle to the framework queue object from which a specified I/O request was delivered.
old-location: wdf\wdfrequestgetioqueue.htm
old-project: wdf
ms.assetid: 9b7d67a3-2899-47b1-9652-d3696d37ec2d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFREQUESTGETIOQUEUE
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
req.alt-api: WdfRequestGetIoQueue
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
req.typenames: *PWDF_QUERY_INTERFACE_CONFIG, WDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# PFN_WDFREQUESTGETIOQUEUE function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestGetIoQueue</b> method returns a handle to the framework queue object from which a specified I/O request was delivered.



## -syntax

````
WDFQUEUE WdfRequestGetIoQueue(
  _In_ WDFREQUEST Request
);
````


## -parameters

### -param Request [in]

A handle to a framework request object.


## -returns
<b>WdfRequestGetIoQueue</b> returns a handle to a framework queue object. If the request was created by the driver, or if the driver has already completed the specified I/O request, the method returns <b>NULL</b>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
For more information about <b>WdfRequestGetIoQueue</b>, see <a href="https://msdn.microsoft.com/a686ea00-6987-480a-a4ce-892e1efbed87">Obtaining Information About an I/O Request</a>.

The following code example obtains a handle to the device object that represents the device that a request belongs to.


## -see-also
<dl>
<dt>
<a href="..\wdfio\nf-wdfio-wdfioqueuegetdevice.md">WdfIoQueueGetDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestGetIoQueue method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

