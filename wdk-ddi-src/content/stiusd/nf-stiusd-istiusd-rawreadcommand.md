---
UID: NF:stiusd.IStiUSD.RawReadCommand
title: IStiUSD::RawReadCommand method
author: windows-driver-content
description: A still image minidriver's IStiUSD::RawReadCommand method reads command information from a still image device.
old-location: image\istiusd_rawreadcommand.htm
old-project: image
ms.assetid: 603f8b76-eb3b-41aa-932c-322f5405a29b
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IStiUSD, IStiUSD interface [Imaging Devices], RawReadCommand method, IStiUSD::RawReadCommand, RawReadCommand method [Imaging Devices], RawReadCommand method [Imaging Devices], IStiUSD interface, RawReadCommand,IStiUSD.RawReadCommand, image.istiusd_rawreadcommand, stifnc_911a418d-3e30-4ddd-b40e-68ed302f18bb.xml, stiusd/IStiUSD::RawReadCommand
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
-	IStiUSD.RawReadCommand
product:
- Windows
targetos: Windows
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---


# IStiUSD::RawReadCommand method
A still image minidriver's <b>IStiUSD::RawReadCommand</b> method reads command information from a still image device.

## Syntax

```
HRESULT RawReadCommand(
  LPVOID       lpBuffer,
  LPDWORD      lpdwNumberOfBytes,
  LPOVERLAPPED lpOverlapped
);
```

## Parameters

`lpBuffer`

Caller-supplied pointer to a buffer to receive data read from the device.

`lpdwNumberOfBytes`

Caller-supplied pointer to a DWORD. The caller loads the DWORD with the number of bytes in the buffer pointed to by <i>lpBuffer</i>. The driver must replace this value with the number of bytes actually read.

`lpOverlapped`

Optional, caller-supplied pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).


## Return Value

If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## Remarks

It is only necessary to implement <b>IStiUSD::RawReadCommand</b> if command and data information are read from a device by different methods. For other devices, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543834">IStiUSD::RawReadData</a> can be used for both commands and data. If the call is not implemented, it must return STIERR_UNSUPPORTED.

Implementation of this method, along with the meaning of buffer contents, are vendor-defined.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | stiusd.h (include Stiusd.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543758">IStiDevice::RawReadCommand</a>



<a href="https://msdn.microsoft.com/62740263-5bbb-48e1-be3d-9ee9cb37d6b9">IStiUSD</a>