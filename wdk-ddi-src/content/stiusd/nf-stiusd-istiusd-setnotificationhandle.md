---
UID: NF:stiusd.IStiUSD.SetNotificationHandle
title: IStiUSD::SetNotificationHandle method
author: windows-driver-content
description: A still image minidriver's IStiUSD::SetNotificationHandle method specifies an event handle that the minidriver should use to inform the caller of device events.
old-location: image\istiusd_setnotificationhandle.htm
old-project: image
ms.assetid: 096e9b7a-fc50-46a2-b67a-7128dba13321
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IStiUSD, IStiUSD interface [Imaging Devices], SetNotificationHandle method, IStiUSD::SetNotificationHandle, SetNotificationHandle method [Imaging Devices], SetNotificationHandle method [Imaging Devices], IStiUSD interface, SetNotificationHandle,IStiUSD.SetNotificationHandle, image.istiusd_setnotificationhandle, stifnc_f6b96be7-54e0-4cf1-a895-3d8d31dbc72b.xml, stiusd/IStiUSD::SetNotificationHandle
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
-	stiusd.h
api_name:
-	IStiUSD.SetNotificationHandle
product: Windows
targetos: Windows
req.typenames: STI_WIA_DEVICE_INFORMATIONW, *PSTI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---


# SetNotificationHandle method
A still image minidriver's <b>IStiUSD::SetNotificationHandle</b> method specifies an event handle that the minidriver should use to inform the caller of device events.

## Syntax

````
HRESULT SetNotificationHandle(
   HANDLE hEvent
);
````

## Parameters

`hEvent`

Caller-supplied handle to a Win32 event, created by calling <b>CreateEvent</b>.


## Return Value

If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## Remarks

If the driver (and device) supports asynchronous notification of <a href="https://msdn.microsoft.com/5f9be89c-8442-4894-b2f6-a4d3558464bf">Still Image Device Events</a>, the minidriver's <b>IStiUSD::SetNotificationHandle</b> method is the means by which the event monitor requests the driver to notify it when an event occurs.

If <i>hEvent</i> is an event handle, the <b>IStiUSD::SetNotificationHandle</b> method should store the handle and use it as an input argument to <b>SetEvent</b> (described in the Microsoft Windows SDK documentation). The driver should call <b>SetEvent</b> each time a device event is detected, to notify the event monitor that an event has occurred.

If <i>hEvent</i> is <b>NULL</b>, the method should disable notification of device events.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | stiusd.h (include Stiusd.h) |
| **Library** | stiusd.h |