---
UID: NF:stiusd.IStiUSD.RawWriteData
title: IStiUSD::RawWriteData method
author: windows-driver-content
description: A still image minidriver's IStiUSD::RawWriteData method writes data to a still image device.
old-location: image\istiusd_rawwritedata.htm
old-project: image
ms.assetid: 82700669-b98f-486c-a7a6-cd7138300f11
ms.author: windowsdriverdev
ms.date: 2/27/2018
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
req.lib: 
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


# IStiUSD::RawWriteData method
A still image minidriver's <b>IStiUSD::RawWriteData</b> method writes data to a still image device.

## Syntax

```
HRESULT RawWriteData(
  LPVOID       lpBuffer,
  DWORD        nNumberOfBytes,
  LPOVERLAPPED lpOverlapped
);
```

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

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543764">IStiDevice::RawWriteData</a>



<a href="https://msdn.microsoft.com/62740263-5bbb-48e1-be3d-9ee9cb37d6b9">IStiUSD</a>