---
UID: NF:sti.IStiDevice.Subscribe
title: IStiDevice::Subscribe method
author: windows-driver-content
description: The IStiDevice::Subscribe method registers the caller to receive notifications of device events.
old-location: image\istidevice_subscribe.htm
old-project: image
ms.assetid: 6266b311-6846-4615-a686-b68b00001fe7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IStiDevice, IStiDevice::Subscribe, Subscribe
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
req.alt-api: IStiDevice.Subscribe
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

# IStiDevice::Subscribe method



## -description
The<b> IStiDevice::Subscribe</b> method registers the caller to receive notifications of device events.



## -syntax

````
HRESULT Subscribe(
  [in, out] LPSTISUBSCRIBE lpSubscribe
);
````


## -parameters

### -param lpSubscribe [in, out]

Caller-supplied pointer to an <a href="..\sti\ns-sti-_stisubscribe.md">STISUBSCRIBE</a> structure containing subscription parameter values.


## -returns
If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.


## -remarks
The<b> IStiDevice::Subscribe</b> method is typically called by applications that intercept events from devices and reroute them. The method allows these applications to be notified of <a href="https://msdn.microsoft.com/5f9be89c-8442-4894-b2f6-a4d3558464bf">Still Image Device Events</a> so they can then dispatch control to appropriate display applications.

Based on contents supplied in the <a href="..\sti\ns-sti-_stisubscribe.md">STISUBSCRIBE</a> structure, the caller can request to be notified of device events by Windows messages or by Win32 events (by means of <b>SetEvent</b> calls).

When the application receives notification of an event, it can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543751">IStiDevice::GetLastNotificationData</a> to find out which event occurred. 

Before calling <b>IStiDevice::Subscribe</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.


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

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543773">IStiDevice::UnSubscribe</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543796">IStillImage::LaunchApplicationForDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiDevice::Subscribe method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

