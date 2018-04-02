---
UID: NF:stiusd.IStiUSD.DeviceReset
title: IStiUSD::DeviceReset method
author: windows-driver-content
description: A still image minidriver's IStiUSD::DeviceReset method resets a still image device to a known, initialized state.
old-location: image\istiusd_devicereset.htm
old-project: image
ms.assetid: f6944297-9aca-4912-a398-c5f3a3e8d4b4
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: DeviceReset method [Imaging Devices], DeviceReset method [Imaging Devices], IStiUSD interface, DeviceReset,IStiUSD.DeviceReset, IStiUSD, IStiUSD interface [Imaging Devices], DeviceReset method, IStiUSD::DeviceReset, image.istiusd_devicereset, stifnc_94561ed6-1f7a-411e-b699-37d56165b2f7.xml, stiusd/IStiUSD::DeviceReset
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
-	Stiusd.h
api_name:
-	IStiUSD.DeviceReset
product: Windows
targetos: Windows
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---


# IStiUSD::DeviceReset method
A still image minidriver's <b>IStiUSD::DeviceReset</b> method resets a still image device to a known, initialized state.

## Syntax

```
HRESULT DeviceReset(

);
```

## Parameters

This function has no parameters.

## Return Value

If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | stiusd.h (include Stiusd.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543733">IStiDevice::DeviceReset</a>



<a href="https://msdn.microsoft.com/62740263-5bbb-48e1-be3d-9ee9cb37d6b9">IStiUSD</a>