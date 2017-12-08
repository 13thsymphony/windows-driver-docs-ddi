---
UID: NF.storport.StorPortBusy
title: StorPortBusy function
author: windows-driver-content
description: The StorPortBusy routine notifies the port driver that the adapter is currently busy, handling outstanding requests.
old-location: storage\storportbusy.htm
old-project: storage
ms.assetid: 81e5b26d-78b5-4ee7-a47c-fc92d01752d1
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: StorPortBusy
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortBusy
req.alt-loc: Storport.lib,Storport.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# StorPortBusy function



## -description
The <b>StorPortBusy</b> routine notifies the port driver that the adapter is currently busy, handling outstanding requests. 


## -syntax

````
STORPORT_API BOOLEAN StorPortBusy(
  _In_ PVOID HwDeviceExtension,
  _In_ ULONG RequestsToComplete
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="storage.storportinitialize">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 

### -param RequestsToComplete [in]

Indicates the number of requests that the adapter must complete before resuming I/O requests to the miniport driver. If <i>RequestsToComplete</i> is greater than the number of currently outstanding requests, the Storport driver will complete all outstanding requests to the adapter before resuming requests. 

## -returns
<b>StorPortBusy</b> returns <b>TRUE</b> if the miniport driver succeeded in notifying the port driver, <b>FALSE</b> if not.

## -remarks
The Storport driver will hold any number of requests until the adapter has completed enough outstanding requests so that it may continue processing requests. 

The library of support routines provided by the SCSI Port driver does not include any routine similar to this one. This functionality is only available with the Storport driver library. 

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
Header
</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Storport.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.storportready">StorPortReady</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortBusy routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
