---
UID: NF:udecxusbendpoint.UdecxUsbEndpointPurgeComplete
title: UdecxUsbEndpointPurgeComplete function
author: windows-driver-content
description: Completes an asynchronous request for canceling all I/O requests queued to the specified endpoint.
old-location: buses\udecxusbendpointpurgecomplete.htm
old-project: usbref
ms.assetid: 91257BC3-C469-44D5-96E2-D1FA599963F1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UdecxUsbEndpointPurgeComplete, UdecxUsbEndpointPurgeComplete function [Buses], buses.udecxusbendpointpurgecomplete, udecxusbendpoint/UdecxUsbEndpointPurgeComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: udecxusbendpoint.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Udecxstub.lib
-	Udecxstub.dll
api_name:
-	UdecxUsbEndpointPurgeComplete
product: Windows
targetos: Windows
req.typenames: UDECX_USB_ENDPOINT_INIT_AND_METADATA, *PUDECX_USB_ENDPOINT_INIT_AND_METADATA
req.product: Windows 10 or later.
---


# UdecxUsbEndpointPurgeComplete function
Completes an asynchronous request for canceling all I/O requests queued to the specified endpoint.

## Syntax

````
FORCEINLINE void UdecxUsbEndpointPurgeComplete(
  _In_ UDECXUSBENDPOINT UdecxUsbEndpoint
);
````

## Parameters

`UdecxUsbEndpoint`

A handle to a UDE endpoint object. The client driver retrieved this pointer in the previous call to <a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointcreate.md">UdecxUsbEndpointCreate</a>.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Header** | udecxusbendpoint.h (include Udecx.h) |
| **Library** | Udecxstub.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="..\udecxusbendpoint\nc-udecxusbendpoint-evt_udecx_usb_endpoint_purge.md">EVT_UDECX_USB_ENDPOINT_PURGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbEndpointPurgeComplete function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>