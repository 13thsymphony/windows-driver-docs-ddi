---
UID: NF:sti.IStillImageW.GetSTILaunchInformation
title: IStillImageW::GetSTILaunchInformation method
author: windows-driver-content
description: The IStillImage::GetSTILaunchInformation method returns the reason the calling still image application was started, if the still image event monitor started it.
old-location: image\istillimage_getstilaunchinformation.htm
old-project: image
ms.assetid: cfcd6e2d-541a-4a28-b2c7-409eb10bcf1e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetSTILaunchInformation method [Imaging Devices], GetSTILaunchInformation method [Imaging Devices], IStillImageW interface, GetSTILaunchInformation,IStillImageW.GetSTILaunchInformation, IStillImageW, IStillImageW interface [Imaging Devices], GetSTILaunchInformation method, IStillImageW::GetSTILaunchInformation, image.istillimage_getstilaunchinformation, sti/IStillImageW::GetSTILaunchInformation, stifnc_b73269ec-512a-4d07-a43a-8c72a28a751b.xml
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
-	IStillImageW.GetSTILaunchInformation
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---


# GetSTILaunchInformation method
The <b>IStillImage::GetSTILaunchInformation</b> method returns the reason the calling still image application was started, if the still image event monitor started it.

## Syntax

````
HRESULT GetSTILaunchInformation(
  [out]           LPWSTR pwszDeviceName,
  [out, optional] DWORD  *pdwEventCode,
  [out]           LPWSTR pwszEventName
);
````

## Parameters

`pwszDeviceName`

Caller-supplied pointer to a buffer, STI_MAX_INTERNAL_NAME_LENGTH bytes in length, to receive the internal device name of the still image device for which the application was started.

`pdwEventCode`

Reserved for future use.

`pwszEventName`

Caller-supplied pointer to a buffer that is large enough to receive a string representation of a GUID. The GUID represents the <a href="https://msdn.microsoft.com/5f9be89c-8442-4894-b2f6-a4d3558464bf">Still Image Device Events</a> for which the application was started.


## Return Value

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## Remarks

If the still image event monitor started the application, the <i>pwszDeviceName</i> and <i>pwszEventName</i> values identify the <b>/StiDevice</b> and <b>/StiEvent</b> command-line arguments (see the description of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543798">IStillImage::RegisterLaunchApplication</a>). If the event monitor did not start the application, the method returns STIERR_GENERIC.

Before calling <b>IStillImage::GetSTILaunchInformation</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543804">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sti.h (include Sti.h) |
| **Library** | sti.h |