---
UID: NF:sti.IStiDevice.GetCapabilities
title: IStiDevice::GetCapabilities method
author: windows-driver-content
description: The IStiDevice::GetCapabilities method returns a still image device's capabilities.
old-location: image\istidevice_getcapabilities.htm
old-project: image
ms.assetid: 4c5d8834-a78d-443e-bfec-1d9fcddb9331
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetCapabilities method [Imaging Devices], GetCapabilities method [Imaging Devices], IStiDevice interface, GetCapabilities,IStiDevice.GetCapabilities, IStiDevice, IStiDevice interface [Imaging Devices], GetCapabilities method, IStiDevice::GetCapabilities, image.istidevice_getcapabilities, sti/IStiDevice::GetCapabilities, stifnc_00882aa7-e8cd-4218-9d05-b9d1f56a6652.xml
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
-	IStiDevice.GetCapabilities
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---


# IStiDevice::GetCapabilities method
The <b>IStiDevice::GetCapabilities</b> method returns a still image device's capabilities.

## Syntax

```
HRESULT GetCapabilities(
  PSTI_DEV_CAPS pDevCaps
);
```

## Parameters

`pDevCaps`

Caller-supplied pointer to an empty <a href="https://msdn.microsoft.com/library/windows/hardware/ff548380">STI_DEV_CAPS</a> structure.


## Return Value

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## Remarks

The <b>IStiDevice::GetCapabilities</b> method returns device capability flags in the caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff548380">STI_DEV_CAPS</a> structure.

Before calling <b>IStiDevice::GetCapabilities</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sti.h (include Sti.h) |