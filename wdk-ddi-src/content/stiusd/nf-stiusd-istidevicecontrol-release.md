---
UID: NF:stiusd.IStiDeviceControl.Release
title: IStiDeviceControl::Release method
author: windows-driver-content
description: The IStiDeviceControl::Release method closes the instance of the COM object that was created when a minidriver client called IStiUSD::Initialize.
old-location: image\istidevicecontrol_release.htm
old-project: image
ms.assetid: 56c2ddc0-9f25-4d4f-9f6e-d8c96c9acc91
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IStiDeviceControl, IStiDeviceControl::Release, Release
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
req.alt-api: IStiDeviceControl.Release
req.alt-loc: Stiusd.h
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
req.typenames: *PSTI_WIA_DEVICE_INFORMATIONW, STI_WIA_DEVICE_INFORMATIONW
req.product: Windows 10 or later.
---

# IStiDeviceControl::Release method



## -description
The <b>IStiDeviceControl::Release</b> method closes the instance of the COM object that was created when a minidriver client called <a href="https://msdn.microsoft.com/library/windows/hardware/ff543824">IStiUSD::Initialize</a>.



## -syntax

````
HRESULT Release();
````


## -parameters


## -returns
If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>Stierr.h</i>.

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>Stierr.h</i>.

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>Stierr.h</i>.


## -remarks
The <b>IStiDeviceControl::Release</b> method should be called from within the destructor function of a user-mode still image minidriver's <b>IStiUSD</b> interface. (For more information, see <a href="https://msdn.microsoft.com/94fdbeba-5b4a-4b66-b381-ec362b6d38c9">Creating a User-Mode Still Image Minidriver</a>.)

A still image minidriver receives an <b>IStiDeviceControl</b> interface pointer as input to its <a href="https://msdn.microsoft.com/library/windows/hardware/ff543824">IStiUSD::Initialize</a> method.


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542933">IStiDeviceControl::AddRef</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiDeviceControl::Release method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

