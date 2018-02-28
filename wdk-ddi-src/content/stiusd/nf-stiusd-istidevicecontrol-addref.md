---
UID: NF:stiusd.IStiDeviceControl.AddRef
title: IStiDeviceControl::AddRef method
author: windows-driver-content
description: The IStiDeviceControl::AddRef method increments the reference count for the IStiDeviceControl interface.
old-location: image\istidevicecontrol_addref.htm
old-project: image
ms.assetid: 8aa28efb-a030-4fed-b9f2-0e67ff1e7c9e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AddRef method [Imaging Devices], AddRef method [Imaging Devices], IStiDeviceControl interface, AddRef,IStiDeviceControl.AddRef, IStiDeviceControl, IStiDeviceControl interface [Imaging Devices], AddRef method, IStiDeviceControl::AddRef, image.istidevicecontrol_addref, stifnc_b0cd1dfe-9e37-42a5-83e0-d0f97c9439e8.xml, stiusd/IStiDeviceControl::AddRef
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
-	IStiDeviceControl.AddRef
product: Windows
targetos: Windows
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---


# AddRef method
The <b>IStiDeviceControl::AddRef</b> method increments the reference count for the <b>IStiDeviceControl</b> interface.

## Syntax

````
HRESULT AddRef();
````

## Parameters

This function has no parameters.

## Return Value

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## Remarks

The <b>IStiDeviceControl::AddRef</b> method should be called from within a user-mode still image minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff543824">IStiUSD::Initialize</a> method.

A still image minidriver receives an <b>IStiDeviceControl</b> interface pointer as an input argument to its <a href="https://msdn.microsoft.com/library/windows/hardware/ff543824">IStiUSD::Initialize</a> method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | stiusd.h (include Stiusd.h) |
| **Library** | stiusd.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543725">IStiDeviceControl::Release</a>



<a href="..\stiusd\nn-stiusd-istidevicecontrol.md">IStiDeviceControl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiDeviceControl::AddRef method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>