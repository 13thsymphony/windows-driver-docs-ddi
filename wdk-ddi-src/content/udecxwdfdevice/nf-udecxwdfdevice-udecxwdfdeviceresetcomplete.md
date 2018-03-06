---
UID: NF:udecxwdfdevice.UdecxWdfDeviceResetComplete
title: UdecxWdfDeviceResetComplete function
author: windows-driver-content
description: Informs the USB device emulation class extension (UdeCx) that the reset operation on the specified controller has competed.
old-location: buses\udecxwdfdeviceresetcomplete.htm
old-project: usbref
ms.assetid: B5873B19-17EF-4DF8-A3E7-7E7F6440A2B7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UdecxWdfDeviceResetComplete, UdecxWdfDeviceResetComplete function [Buses], buses.udecxwdfdeviceresetcomplete, udecxwdfdevice/UdecxWdfDeviceResetComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: udecxwdfdevice.h
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Udecxstub.lib
-	Udecxstub.dll
api_name:
-	UdecxWdfDeviceResetComplete
product: Windows
targetos: Windows
req.typenames: UDECX_WDF_DEVICE_RESET_ACTION, *PUDECX_WDF_DEVICE_RESET_ACTION
req.product: Windows 10 or later.
---


# UdecxWdfDeviceResetComplete function
Informs the  USB device emulation  class extension (UdeCx) that the reset operation on the specified controller has competed.

## Syntax

````
void UdecxWdfDeviceResetComplete(
  _In_ WDFDEVICE Device
);
````

## Parameters

`UdeWdfDevice`

TBD


## Return Value

This function does not return a value.

## Remarks

When the class extension calls the  <a href="..\udecxwdfdevice\nc-udecxwdfdevice-evt_udecx_wdf_device_reset.md">EVT_UDECX_WDF_DEVICE_RESET</a> callback function, that call is asynchronous. The client driver must call  <b>UdecxWdfDeviceResetComplete</b> to notify the class extension when the reset operation is complete with appropriate status information.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Header** | udecxwdfdevice.h (include Udecx.h) |
| **Library** | Udecxstub.lib |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\udecxwdfdevice\nc-udecxwdfdevice-evt_udecx_wdf_device_reset.md">EVT_UDECX_WDF_DEVICE_RESET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxWdfDeviceResetComplete function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>