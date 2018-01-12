---
UID: NF:sti.IStiDevice.GetLastNotificationData
title: IStiDevice::GetLastNotificationData method
author: windows-driver-content
description: The IStiDevice::GetLastNotificationData method returns a description of the most recent event that occurred on a still image device.
old-location: image\istidevice_getlastnotificationdata.htm
old-project: image
ms.assetid: dd073fde-d2ba-45c0-a52c-22e86718901a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IStiDevice, IStiDevice::GetLastNotificationData, GetLastNotificationData
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
req.alt-api: IStiDevice.GetLastNotificationData
req.alt-loc: sti.h
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
req.typenames: STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# IStiDevice::GetLastNotificationData method



## -description
The <b>IStiDevice::GetLastNotificationData</b> method returns a description of the most recent event that occurred on a still image device.



## -syntax

````
HRESULT GetLastNotificationData(
  [out] LPSTINOTIFY lpNotify
);
````


## -parameters

### -param lpNotify [out]

Caller-supplied pointer to an <a href="..\sti\ns-sti-_stinotify.md">STINOTIFY</a> structure to receive event information.


## -returns
If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.


## -remarks
Each time a <a href="https://msdn.microsoft.com/5f9be89c-8442-4894-b2f6-a4d3558464bf">Still Image Device Events</a> occurs, the still image event monitor calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff543821">IStiUSD::GetNotificationData</a> (exported by a vendor-supplied minidriver) to obtain an event description. These descriptions are added to a linked list. If a client of the <b>IStiDevice</b> COM interface has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff543768">IStiDevice::Subscribe</a>, it is notified each time a device event occurs. It can then call <b>IStiDevice::GetLastNotificationData</b> to obtain the most recent addition to the linked list of events.

Before calling <b>IStiDevice::GetLastNotificationData</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Sti.h (include Sti.h)</dt>
</dl>
</td>
</tr>
</table>