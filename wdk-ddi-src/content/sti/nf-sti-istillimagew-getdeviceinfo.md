---
UID: NF:sti.IStillImageW.GetDeviceInfo
title: IStillImageW::GetDeviceInfo method
author: windows-driver-content
description: The IStillImage::GetDeviceInfo method returns hardware characteristics for a specified still image device.
old-location: image\istillimage_getdeviceinfo.htm
old-project: image
ms.assetid: 4f3e1dcd-1885-4b9f-b033-19d91178d8ab
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetDeviceInfo method [Imaging Devices], GetDeviceInfo method [Imaging Devices], IStillImageW interface, GetDeviceInfo,IStillImageW.GetDeviceInfo, IStillImageW, IStillImageW interface [Imaging Devices], GetDeviceInfo method, IStillImageW::GetDeviceInfo, image.istillimage_getdeviceinfo, sti/IStillImageW::GetDeviceInfo, stifnc_a6d46551-9c0a-41f2-a5ed-ca5bc4d1b8c1.xml
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
req.lib: sti.h
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
-	IStillImageW.GetDeviceInfo
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---


# GetDeviceInfo method
The <b>IStillImage::GetDeviceInfo</b> method returns hardware characteristics for a specified still image device.

## Syntax

````
HRESULT GetDeviceInfo(
  [in]  LPWSTR pwszDeviceName,
  [out] LPVOID *ppBuffer
);
````

## Parameters

`pwszDeviceName`

Caller-supplied pointer to a string representing an internal device name, obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543790">IStillImage::GetSTILaunchInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543784">IStillImage::GetDeviceList</a>.

`ppBuffer`

Receives a handle to an <a href="..\sti\ns-sti-_sti_device_informationw.md">STI_DEVICE_INFORMATION</a> structure.


## Return Value

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## Remarks

The <b>IStillImage::GetDeviceInfo</b> method returns an <a href="..\sti\ns-sti-_sti_device_informationw.md">STI_DEVICE_INFORMATION</a> structure for the specified still-image device. Structure contents are typically used for creating user interface displays.

Before calling <b>IStillImage::GetDeviceInfo</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543804">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.

When the caller has finished using the STI_DEVICE_INFORMATION structure referenced by <i>ppBuffer</i>, it must deallocate the buffer by calling <b>LocalFree</b> (described in the Microsoft Windows SDK documentation).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sti.h (include Sti.h) |
| **Library** | sti.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543784">IStillImage::GetDeviceList</a>



<a href="..\sti\nn-sti-istillimagew.md">IStillImageW</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStillImageW::GetDeviceInfo method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>