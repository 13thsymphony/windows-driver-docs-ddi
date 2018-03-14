---
UID: NF:sti.IStiDevice.GetLastErrorInfo
title: IStiDevice::GetLastErrorInfo method
author: windows-driver-content
description: The IStiDevice::GetLastErrorInfo method returns information about the last known error associated with a still image device.
old-location: image\istidevice_getlasterrorinfo.htm
old-project: image
ms.assetid: de2f8897-c75f-4c37-aecb-f36d0f9933f9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetLastErrorInfo method [Imaging Devices], GetLastErrorInfo method [Imaging Devices], IStiDevice interface, GetLastErrorInfo,IStiDevice.GetLastErrorInfo, IStiDevice, IStiDevice interface [Imaging Devices], GetLastErrorInfo method, IStiDevice::GetLastErrorInfo, image.istidevice_getlasterrorinfo, sti/IStiDevice::GetLastErrorInfo, stifnc_f54b574c-5894-4029-888c-fe60738858d7.xml
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
-	IStiDevice.GetLastErrorInfo
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---


# GetLastErrorInfo method
The <b>IStiDevice::GetLastErrorInfo</b> method returns information about the last known error associated with a still image device.

## Syntax

````
HRESULT GetLastErrorInfo(
  [out] STI_ERROR_INFO *pLastErrorInf
);
````

## Parameters

`pLastErrorInfo`




## Return Value

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## Remarks

The <b>IStiDevice::GetLastErrorInfo</b> method returns information about the most recent error by filling in the caller-supplied <a href="..\sti\ns-sti-_error_infow.md">STI_ERROR_INFO</a> structure. The method calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff543820">IStiUSD::GetLastErrorInfo</a>, which is exported by vendor-supplied minidrivers.

Before calling <b>IStiDevice::GetLastErrorInfo</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sti.h (include Sti.h) |