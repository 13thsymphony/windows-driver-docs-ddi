---
UID: NF.stiusd.IStiUSD.RawReadData
title: IStiUSD::RawReadData method
author: windows-driver-content
description: A still image minidriver's IStiUSD::RawReadData method reads data from a still image device.
old-location: image\istiusd_rawreaddata.htm
old-project: Image
ms.assetid: 6ae64309-da53-420b-bf87-e8924e902dba
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IStiUSD, IStiUSD::RawReadData, RawReadData
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
req.alt-api: IStiUSD.RawReadData
req.alt-loc: stiusd.h
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
req.product: Windows 10 or later.
---

# IStiUSD::RawReadData method



## -description
A still image minidriver's <b>IStiUSD::RawReadData</b> method reads data from a still image device.



## -syntax

````
HRESULT RawReadData(
   LPVOID       lpBuffer,
   LPDWORD      lpdwNumberOfBytes,
   LPOVERLAPPED lpOverlapped
);
````


## -parameters

### -param lpBuffer 

Caller-supplied pointer to a buffer to receive data read from the device.


### -param lpdwNumberOfBytes 

Caller-supplied pointer to a DWORD. The caller loads the DWORD with the number of bytes in the buffer pointed to by <i>lpBuffer</i>. The driver must replace this value with the number of bytes actually read.


### -param lpOverlapped 

Optional, caller-supplied pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).


## -returns
If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.


## -remarks
A still image minidriver typically implements this method by calling <b>ReadFile</b> (described in the Windows SDK documentation).

For USB devices, better performance can be achieved if read requests are aligned to maximum packet size boundaries. Maximum packet sizes can be obtained by calling <a href="base.deviceiocontrol">DeviceIoControl</a>, specifying the <a href="..\usbscan\ni-usbscan-ioctl_get_channel_align_rqst.md">IOCTL_GET_CHANNEL_ALIGN_RQST</a> I/O control code.


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
<dt>Stiusd.h (include Stiusd.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="image.istidevice_rawreaddata">IStiDevice::RawReadData</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20IStiUSD::RawReadData method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

