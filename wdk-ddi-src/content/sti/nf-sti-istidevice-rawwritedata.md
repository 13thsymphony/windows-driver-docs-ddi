---
UID: NF.sti.IStiDevice.RawWriteData
title: IStiDevice::RawWriteData method
author: windows-driver-content
description: The IStiDevice::RawWriteData method writes data to a still image device.
old-location: image\istidevice_rawwritedata.htm
old-project: Image
ms.assetid: bc64b3d6-8c86-4f99-b3b9-de31f576988c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IStiDevice, IStiDevice::RawWriteData, RawWriteData
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
req.alt-api: IStiDevice.RawWriteData
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
req.product: Windows 10 or later.
---

# IStiDevice::RawWriteData method



## -description
The <b>IStiDevice::RawWriteData</b> method writes data to a still image device.



## -syntax

````
HRESULT RawWriteData(
  [in]           LPVOID       lpBuffer,
                 DWORD        nNumberOfBytes,
  [in, optional] LPOVERLAPPED lpOverlapped
);
````


## -parameters

### -param lpBuffer [in]

Caller-supplied pointer to a buffer containing data to be sent to the device.


### -param nNumberOfBytes 

Caller-supplied number of bytes to be written. This is the number of bytes in the buffer pointed to by <i>lpBuffer</i>.


### -param lpOverlapped [in, optional]

Optional, caller-supplied pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).


## -returns
If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.


## -remarks
The <b>IStiDevice::RawWriteData</b> method calls <a href="image.istiusd_rawwritedata">IStiUSD::RawWriteData</a>, which is exported by vendor-supplied minidrivers.

Before calling <b>IStiDevice::RawWriteData</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="image.istillimage_createdevice">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.

A call to <b>IStiDevice::RawWriteData</b> must be preceded by a call to <a href="image.istidevice_lockdevice">IStiDevice::LockDevice</a> and followed by a call to <a href="image.istidevice_unlockdevice">IStiDevice::UnLockDevice</a>.


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
<a href="image.istidevice_rawwritecommand">IStiDevice::RawWriteCommand</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20IStiDevice::RawWriteData method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

