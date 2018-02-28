---
UID: NF:stiusd.IStiUSD.RawWriteData
title: IStiUSD::RawWriteData method
author: windows-driver-content
description: A still image minidriver's IStiUSD::RawWriteData method writes data to a still image device.
old-location: image\istiusd_rawwritedata.htm
old-project: image
ms.assetid: 82700669-b98f-486c-a7a6-cd7138300f11
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IStiUSD, IStiUSD interface [Imaging Devices], RawWriteData method, IStiUSD::RawWriteData, RawWriteData method [Imaging Devices], RawWriteData method [Imaging Devices], IStiUSD interface, RawWriteData,IStiUSD.RawWriteData, image.istiusd_rawwritedata, stifnc_32bdc55e-1e54-44ba-be36-e851d333f207.xml, stiusd/IStiUSD::RawWriteData
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
-	IStiUSD.RawWriteData
product: Windows
targetos: Windows
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---


# RawWriteData method
A still image minidriver's <b>IStiUSD::RawWriteData</b> method writes data to a still image device.

## Syntax

````
HRESULT RawWriteData(
   LPVOID       lpBuffer,
   DWORD        dwNumberOfBytes,
   LPOVERLAPPED lpOverlapped
);
````

## Parameters

`lpBuffer`

Caller-supplied pointer to a buffer containing data to be sent to the device.

`nNumberOfBytes`



`lpOverlapped`

Optional, caller-supplied pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).


## Return Value

If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## Remarks

A still image minidriver typically implements this method by calling <b>WriteFile</b> (described in the Windows SDK documentation).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | stiusd.h (include Stiusd.h) |
| **Library** | stiusd.h |

## See Also

<a href="..\stiusd\nn-stiusd-istiusd.md">IStiUSD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543764">IStiDevice::RawWriteData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiUSD::RawWriteData method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>