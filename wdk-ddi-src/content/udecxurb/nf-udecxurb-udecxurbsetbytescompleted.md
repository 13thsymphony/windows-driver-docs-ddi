---
UID: NF:udecxurb.UdecxUrbSetBytesCompleted
title: UdecxUrbSetBytesCompleted function
author: windows-driver-content
description: Sets the number of bytes transferred for the URB contained within a framework request object.
old-location: buses\udecxurbsetbytescompleted.htm
old-project: usbref
ms.assetid: 86C320B0-F679-4A8E-9015-D2BD8059A6CD
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: UdecxUrbSetBytesCompleted function [Buses], UdecxUrbSetBytesCompleted, buses.udecxurbsetbytescompleted, udecxurb/UdecxUrbSetBytesCompleted
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: udecxurb.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Udecxstub.lib
-	Udecxstub.dll
apiname:
-	UdecxUrbSetBytesCompleted
product: Windows
targetos: Windows
req.typenames: USB_DEVICE_PORT_PATH, *PUSB_DEVICE_PORT_PATH
req.product: Windows 10 or later.
---


# UdecxUrbSetBytesCompleted function
Sets the number of bytes transferred for the URB contained within a framework  request object.

## Syntax

````
FORCEINLINE void UdecxUrbSetBytesCompleted(
  _In_ WDFREQUEST Request,
  _In_ PULONG     Length
);
````

## Parameters

`Request`

A handle to a framework request object that contains the <a href="..\usb\ns-usb-_urb.md">URB</a> for the transfer.

`BytesCompleted`

TBD


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Header** | udecxurb.h (include Udecx.h) |
| **Library** | Udecxstub.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUrbSetBytesCompleted function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>