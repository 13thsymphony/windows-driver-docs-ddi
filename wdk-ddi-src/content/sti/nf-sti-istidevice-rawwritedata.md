---
UID: NF:sti.IStiDevice.RawWriteData
title: IStiDevice::RawWriteData method
author: windows-driver-content
description: The IStiDevice::RawWriteData method writes data to a still image device.
old-location: image\istidevice_rawwritedata.htm
old-project: image
ms.assetid: bc64b3d6-8c86-4f99-b3b9-de31f576988c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IStiDevice, IStiDevice interface [Imaging Devices], RawWriteData method, IStiDevice::RawWriteData, RawWriteData method [Imaging Devices], RawWriteData method [Imaging Devices], IStiDevice interface, RawWriteData,IStiDevice.RawWriteData, image.istidevice_rawwritedata, sti/IStiDevice::RawWriteData, stifnc_2b8739f4-3ab7-4b25-bae2-7e025cffe72d.xml
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
-	IStiDevice.RawWriteData
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---


# RawWriteData method
The <b>IStiDevice::RawWriteData</b> method writes data to a still image device.

## Syntax

````
HRESULT RawWriteData(
  [in]           LPVOID       lpBuffer,
                 DWORD        nNumberOfBytes,
  [in, optional] LPOVERLAPPED lpOverlapped
);
````

## Parameters

`lpBuffer`

Caller-supplied pointer to a buffer containing data to be sent to the device.

`nNumberOfBytes`

Caller-supplied number of bytes to be written. This is the number of bytes in the buffer pointed to by <i>lpBuffer</i>.

`lpOverlapped`

Optional, caller-supplied pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).


## Return Value

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## Remarks

The <b>IStiDevice::RawWriteData</b> method calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff543839">IStiUSD::RawWriteData</a>, which is exported by vendor-supplied minidrivers.

Before calling <b>IStiDevice::RawWriteData</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543778">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.

A call to <b>IStiDevice::RawWriteData</b> must be preceded by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543756">IStiDevice::LockDevice</a> and followed by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543770">IStiDevice::UnLockDevice</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | sti.h (include Sti.h) |
| **Library** | sti.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543762">IStiDevice::RawWriteCommand</a>



<a href="..\sti\nn-sti-istidevice.md">IStiDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiDevice::RawWriteData method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>