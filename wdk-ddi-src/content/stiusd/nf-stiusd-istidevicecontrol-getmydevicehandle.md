---
UID: NF:stiusd.IStiDeviceControl.GetMyDeviceHandle
title: IStiDeviceControl::GetMyDeviceHandle method
author: windows-driver-content
description: This topic describes the GetMyDeviceHandle method.
old-location: image\istidevicecontrol_getmydevicehandle.htm
old-project: image
ms.assetid: B20B2AE6-A408-451C-B46D-803139E8B57F
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetMyDeviceHandle method [Imaging Devices], GetMyDeviceHandle method [Imaging Devices], IStiDeviceControl interface, GetMyDeviceHandle,IStiDeviceControl.GetMyDeviceHandle, IStiDeviceControl, IStiDeviceControl interface [Imaging Devices], GetMyDeviceHandle method, IStiDeviceControl::GetMyDeviceHandle, image.istidevicecontrol_getmydevicehandle, stiusd/IStiDeviceControl::GetMyDeviceHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: stiusd.h
req.include-header: 
req.target-type: Windows
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
-	Stiusd.h
api_name:
-	IStiDeviceControl.GetMyDeviceHandle
product: Windows
targetos: Windows
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---


# GetMyDeviceHandle method
This topic describes the <b>GetMyDeviceHandle</b> method.

## Syntax

````
HRESULT GetMyDeviceHandle(
   LPHANDLE lph
);
````

## Parameters

`lph`

Defines the <b>LPHANDLE</b> parameter <i>lph</i>.


## Return Value

Defines the <b>HRESULT</b> return value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | stiusd.h |
| **Library** | stiusd.h |

## See Also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/image/istidevicecontrol-com-interface">IStiDeviceControl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiDeviceControl::GetMyDeviceHandle method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>