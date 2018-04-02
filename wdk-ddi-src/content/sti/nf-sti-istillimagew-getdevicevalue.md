---
UID: NF:sti.IStillImageW.GetDeviceValue
title: IStillImageW::GetDeviceValue method
author: windows-driver-content
description: The IStillImage::GetDeviceValue method returns registry information associated with a specified still image device.
old-location: image\istillimage_getdevicevalue.htm
old-project: image
ms.assetid: 506c50fa-f162-4b30-bfb9-91987e064c39
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetDeviceValue method [Imaging Devices], GetDeviceValue method [Imaging Devices], IStillImageW interface, GetDeviceValue,IStillImageW.GetDeviceValue, IStillImageW, IStillImageW interface [Imaging Devices], GetDeviceValue method, IStillImageW::GetDeviceValue, image.istillimage_getdevicevalue, sti/IStillImageW::GetDeviceValue, stifnc_4b207dea-28ff-4f85-b8a7-43c038b3e810.xml
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
-	IStillImageW.GetDeviceValue
product:
- Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---


# IStillImageW::GetDeviceValue method
The <b>IStillImage::GetDeviceValue</b> method returns registry information associated with a specified still image device.

## Syntax

```
HRESULT GetDeviceValue(
  LPWSTR  pwszDeviceName,
  LPWSTR  pValueName,
  LPDWORD pType,
  LPBYTE  pData,
  LPDWORD cbData
);
```

## Parameters

`pwszDeviceName`

Caller-supplied pointer to a string representing an internal device name, obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543790">IStillImage::GetSTILaunchInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543784">IStillImage::GetDeviceList</a>.

`pValueName`

Caller-supplied pointer to a string representing a registry value name.

`pType`

Receives a constant representing the data type of the returned registry value.

`pData`

Caller-supplied pointer to a buffer to receive a returned value.

`cbData`

Caller-supplied size, in bytes, of the buffer pointed to by <i>pData</i>. The method modifies this value to represent the size of the returned data. If the specified buffer size is too small, the method supplies the required buffer size and returns an error code.


## Return Value

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## Remarks

The purpose of the <b>IStillImage::GetDeviceValue</b> method is to return the values currently assigned to device-specific <a href="https://msdn.microsoft.com/cedc8afc-54c4-485e-989c-481fe30d899b">Registry Entries for Still Image Devices</a>. The method calls <b>RegQueryValueEx</b> (described in the Microsoft Windows SDK documentation).

The <b>IStillImage::GetDeviceValue</b> method can return either an ANSI or a Unicode string. It can return a Unicode string only if your code is built as Unicode with Unicode defined.

Before calling <b>IStillImage::GetDeviceValue</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543804">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sti.h (include Sti.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543801">IStillImage::SetDeviceValue</a>



<a href="https://msdn.microsoft.com/a9ceee48-cbb5-4448-83b4-9c19fe89fcb9">IStillImageW</a>