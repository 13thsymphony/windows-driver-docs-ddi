---
UID: NF:sti.IStiDevice.UnSubscribe
title: IStiDevice::UnSubscribe method
author: windows-driver-content
description: The IStiDevice::UnSubscribe method removes the caller from the list of applications registered to receive notification of device events.
old-location: image\istidevice_unsubscribe.htm
old-project: image
ms.assetid: ee0bfafa-9f4b-4b4a-8b26-4bab81253500
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IStiDevice, IStiDevice interface [Imaging Devices], UnSubscribe method, IStiDevice::UnSubscribe, UnSubscribe method [Imaging Devices], UnSubscribe method [Imaging Devices], IStiDevice interface, UnSubscribe,IStiDevice.UnSubscribe, image.istidevice_unsubscribe, sti/IStiDevice::UnSubscribe, stifnc_8144319d-d1da-40cd-ad1d-6b65c28155be.xml
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
-	Sti.h
api_name:
-	IStiDevice.UnSubscribe
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---


# UnSubscribe method
The<b> IStiDevice::UnSubscribe</b> method removes the caller from the list of applications registered to receive notification of device events.

## Syntax

````
HRESULT UnSubscribe();
````

## Parameters

This function has no parameters.

## Return Value

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## Remarks

Before calling <b>IStiDevice::UnSubscribe</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sti.h (include Sti.h) |
| **Library** | sti.h |

## See Also

<a href="..\sti\nn-sti-istidevice.md">IStiDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543768">IStiDevice::Subscribe</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiDevice::UnSubscribe method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>