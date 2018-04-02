---
UID: NF:sti.IStiDevice.Escape
title: IStiDevice::Escape method
author: windows-driver-content
description: The IStiDevice::Escape method sends a request for a vendor-specific I/O operation to a still image device.
old-location: image\istidevice_escape.htm
old-project: image
ms.assetid: ca2aae12-b4b8-4bae-bc3b-812a1ae539c0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: Escape method [Imaging Devices], Escape method [Imaging Devices], IStiDevice interface, Escape,IStiDevice.Escape, IStiDevice, IStiDevice interface [Imaging Devices], Escape method, IStiDevice::Escape, image.istidevice_escape, sti/IStiDevice::Escape, stifnc_5eb8e67e-67cc-4d04-abff-ada5b42b0004.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: sti.h
req.include-header: Sti.h
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
-	sti.h
api_name:
-	IStiDevice.Escape
product:
- Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---


# IStiDevice::Escape method
The <b>IStiDevice::Escape</b> method sends a request for a vendor-specific I/O operation to a still image device.

## Syntax

```
HRESULT Escape(
  STI_RAW_CONTROL_CODE EscapeFunction,
  LPVOID               lpInData,
  DWORD                cbInDataSize,
  LPVOID               pOutData,
  DWORD                dwOutDataSize,
  LPDWORD              pdwActualData
);
```

## Parameters

`EscapeFunction`

Caller-supplied, vendor-defined, DWORD-sized value representing an I/O operation. The device's minidriver must recognize this value and must export an <b>IStiUSD</b> interface. Vendor-defined values must be greater than STI_RAW_RESERVED, which is defined in <i>Sti.h</i>.

`lpInData`

Caller-supplied pointer to a buffer containing data to be sent to the device.

`cbInDataSize`

Caller-supplied length, in bytes, of the data contained in the buffer pointed to by <i>lpInData</i>.

`pOutData`

Caller-supplied pointer to a memory buffer to receive data from the device.

`dwOutDataSize`

Caller-supplied length, in bytes, of the buffer pointed to by <i>lpOutData</i>.

`pdwActualData`

Receives the number of bytes actually written to <i>pOutData</i>.


## Return Value

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## Remarks

The <b>IStiDevice::Escape</b> method calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff543815">IStiUSD::Escape</a>, which is exported by vendor-supplied minidrivers. The device's minidriver defines the Method parameter usage.

Before calling <b>IStiDevice::Escape</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.

A call to <b>IStiDevice::Escape</b> must be preceded by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543756">IStiDevice::LockDevice</a> and followed by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543770">IStiDevice::UnLockDevice</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sti.h (include Sti.h) |