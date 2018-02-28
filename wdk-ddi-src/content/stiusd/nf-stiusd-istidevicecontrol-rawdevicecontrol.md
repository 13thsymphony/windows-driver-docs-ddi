---
UID: NF:stiusd.IStiDeviceControl.RawDeviceControl
title: IStiDeviceControl::RawDeviceControl method
author: windows-driver-content
description: This topic describes the RawDeviceControl method.
old-location: image\istidevicecontrol_rawdevicecontrol.htm
old-project: image
ms.assetid: 107C7EB4-9C72-49CF-A330-7D517CC67F35
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IStiDeviceControl, IStiDeviceControl interface [Imaging Devices], RawDeviceControl method, IStiDeviceControl::RawDeviceControl, RawDeviceControl method [Imaging Devices], RawDeviceControl method [Imaging Devices], IStiDeviceControl interface, RawDeviceControl,IStiDeviceControl.RawDeviceControl, image.istidevicecontrol_rawdevicecontrol, stiusd/IStiDeviceControl::RawDeviceControl
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
-	IStiDeviceControl.RawDeviceControl
product: Windows
targetos: Windows
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---


# RawDeviceControl method
This topic describes the <b>RawDeviceControl</b> method.

## Syntax

````
HRESULT RawDeviceControl(
   USD_CONTROL_CODE EscapeFunction,
   LPVOID           lpInData,
   DWORD            cbInDataSize,
   LPVOID           pOutData,
   DWORD            dwOutDataSize,
   LPDWORD          pdwActualData
);
````

## Parameters

`EscapeFunction`

Defines the <b>USD_CONTROL_CODE</b> parameter <i>EscapeFunction.</i>

`lpInData`

Defines the <b>LPVOID</b> parameter <i>lpInData.</i>

`cbInDataSize`

Defines the <b>DWORD</b> parameter <i>cbInDataSize.</i>

`pOutData`

Defines the <b>LPVOID</b> parameter <i>pOutData.</i>

`dwOutDataSize`

Defines the <b>DWORD</b> parameter <i>dwOutDataSize.</i>

`pdwActualData`

Defines the <b>LPDWORD</b> parameter <i>pdwActualData.</i>


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiDeviceControl::RawDeviceControl method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>