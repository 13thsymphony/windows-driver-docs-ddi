---
UID: NF:sti.IStiDevice.Release
title: IStiDevice::Release method
author: windows-driver-content
description: The IStiDevice::Release method closes the instance of the COM object that was created by a previous call to IStillImage::CreateDevice, and removes access to the object's interface.
old-location: image\istidevice_release.htm
old-project: image
ms.assetid: cff05099-cf27-4cc6-a820-1d8a5c3ef88e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IStiDevice, IStiDevice interface [Imaging Devices], Release method, IStiDevice::Release, Release method [Imaging Devices], Release method [Imaging Devices], IStiDevice interface, Release,IStiDevice.Release, image.istidevice_release, sti/IStiDevice::Release, stifnc_70352bce-ba09-45c1-97a8-add180942d05.xml
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
-	Sti.h
api_name:
-	IStiDevice.Release
product:
- Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---


# IStiDevice::Release method
The <b>IStiDevice::Release</b> method closes the instance of the COM object that was created by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a>, and removes access to the object's interface.

## Syntax

```
ULONG Release(

);
```

## Parameters

This function has no parameters.

## Return Value

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sti.h (include Sti.h) |