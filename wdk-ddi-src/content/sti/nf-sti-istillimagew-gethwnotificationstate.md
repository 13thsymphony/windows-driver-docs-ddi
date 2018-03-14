---
UID: NF:sti.IStillImageW.GetHwNotificationState
title: IStillImageW::GetHwNotificationState method
author: windows-driver-content
description: The IStillImage::GetHwNotificationState method indicates whether applications will be notified when Still Image Device Events occur on a specified device.
old-location: image\istillimage_gethwnotificationstate.htm
old-project: image
ms.assetid: 8c97c4f0-3cb8-4457-8389-02d9fba51400
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetHwNotificationState method [Imaging Devices], GetHwNotificationState method [Imaging Devices], IStillImageW interface, GetHwNotificationState,IStillImageW.GetHwNotificationState, IStillImageW, IStillImageW interface [Imaging Devices], GetHwNotificationState method, IStillImageW::GetHwNotificationState, image.istillimage_gethwnotificationstate, sti/IStillImageW::GetHwNotificationState, stifnc_9dab6727-1954-4054-b918-be9666c05301.xml
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
-	IStillImageW.GetHwNotificationState
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---


# GetHwNotificationState method
The <b>IStillImage::GetHwNotificationState</b> method indicates whether applications will be notified when <a href="https://msdn.microsoft.com/5f9be89c-8442-4894-b2f6-a4d3558464bf">Still Image Device Events</a> occur on a specified device.

## Syntax

````
HRESULT GetHwNotificationState(
  [in]  LPCWSTR pwszDeviceName,
  [out] BOOL    *pbCurrentState
);
````

## Parameters

`pwszDeviceName`

Caller-supplied pointer to a string representing an internal device name, obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543790">IStillImage::GetSTILaunchInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543784">IStillImage::GetDeviceList</a>.

`pbCurrentState`

Receives <b>TRUE</b> if event notification is enabled, or <b>FALSE</b> otherwise.


## Return Value

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## Remarks

Before calling <b>IStillImage::GetHwNotificationState</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543804">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sti.h (include Sti.h) |

## See Also

<a href="https://msdn.microsoft.com/a9ceee48-cbb5-4448-83b4-9c19fe89fcb9">IStillImageW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543780">IStillImage::EnableHwNotifications</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStillImageW::GetHwNotificationState method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>