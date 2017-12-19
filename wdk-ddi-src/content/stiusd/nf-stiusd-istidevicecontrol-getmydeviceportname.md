---
UID: NF.stiusd.IStiDeviceControl.GetMyDevicePortName
title: IStiDeviceControl::GetMyDevicePortName method
author: windows-driver-content
description: The IStiDeviceControl::GetMyDevicePortName method allows a user-mode still image minidriver to obtain a device's port name.
old-location: image\istidevicecontrol_getmydeviceportname.htm
old-project: Image
ms.assetid: f400ab05-aea9-4154-a725-5b23a6dc06b6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IStiDeviceControl, IStiDeviceControl::GetMyDevicePortName, GetMyDevicePortName
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
req.alt-api: IStiDeviceControl.GetMyDevicePortName
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

# IStiDeviceControl::GetMyDevicePortName method



## -description
The <b>IStiDeviceControl::GetMyDevicePortName</b> method allows a user-mode still image minidriver to obtain a device's port name.



## -syntax

````
HRESULT GetMyDevicePortName(
   LPWSTR lpszDevicePath,
   DWORD  cwDevicePathSize
);
````


## -parameters

### -param lpszDevicePath 

Caller-supplied pointer to a buffer to receive the device's port name.


### -param cwDevicePathSize 

Caller-supplied number of characters (of type TCHAR) in the buffer pointed to by <i>lpszDevicePath</i>.


## -returns
If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.


## -remarks
The path name that a still image minidriver receives by calling <b>IStiDeviceControl::GetMyDevicePortName</b> can be used as an input argument to <a href="fs.createfile">CreateFile</a> (described in the Microsoft Windows SDK documentation).

A still image minidriver receives an <b>IStiDeviceControl</b> interface pointer as an input argument to its <a href="image.istiusd_initialize">IStiUSD::Initialize</a> method.


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