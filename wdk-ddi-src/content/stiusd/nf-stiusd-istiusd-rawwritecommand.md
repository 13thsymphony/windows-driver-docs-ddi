---
UID: NF:stiusd.IStiUSD.RawWriteCommand
title: IStiUSD::RawWriteCommand method
author: windows-driver-content
description: A still image minidriver's IStiDevice::RawWriteCommand method sends command information to a still image device.
old-location: image\istiusd_rawwritecommand.htm
old-project: image
ms.assetid: c1b03ff5-1924-4221-b177-15214a8bf4f1
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IStiUSD, IStiUSD interface [Imaging Devices], RawWriteCommand method, IStiUSD::RawWriteCommand, RawWriteCommand method [Imaging Devices], RawWriteCommand method [Imaging Devices], IStiUSD interface, RawWriteCommand,IStiUSD.RawWriteCommand, image.istiusd_rawwritecommand, stifnc_508a67c1-4f4f-4324-bbb4-fc095fa023c4.xml, stiusd/IStiUSD::RawWriteCommand
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: stiusd.h
req.include-header: Stiusd.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: stiusd.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	stiusd.h
api_name:
-	IStiUSD.RawWriteCommand
product: Windows
targetos: Windows
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---


# RawWriteCommand method
A still image minidriver's <b>IStiDevice::RawWriteCommand</b> method sends command information to a still image device.

## Syntax

````
HRESULT RawWriteCommand(
   LPVOID       lpBuffer,
   DWORD        nNumberOfBytes,
   LPOVERLAPPED lpOverlapped
);
````

## Parameters

`lpBuffer`

Caller-supplied pointer to a buffer containing data to be sent to the device.

`nNumberOfBytes`

Caller-supplied number of bytes to be written. This is the number of bytes in the buffer pointed to by <i>lpBuffer</i>.

`lpOverlapped`

Optional, caller-supplied pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).


## Return Value

If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## Remarks

It is only necessary to call <b>IStiUSD::RawWriteCommand</b> if commands and data are written to a device by different methods. For other devices, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543839">IStiUSD::RawWriteData</a> can be used for both commands and data. If the call is not implemented, it must return STIERR_UNSUPPORTED.

Implementation of this method, along with the meaning of buffer contents, are vendor-defined.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | stiusd.h (include Stiusd.h) |
| **Library** | stiusd.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543762">IStiDevice::RawWriteCommand</a>



<a href="..\stiusd\nn-stiusd-istiusd.md">IStiUSD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiUSD::RawWriteCommand method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>