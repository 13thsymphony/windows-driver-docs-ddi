---
UID: NF.sti.IStiDevice.GetCapabilities
title: IStiDevice::GetCapabilities method
author: windows-driver-content
description: The IStiDevice::GetCapabilities method returns a still image device's capabilities.
old-location: image\istidevice_getcapabilities.htm
old-project: Image
ms.assetid: 4c5d8834-a78d-443e-bfec-1d9fcddb9331
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IStiDevice, IStiDevice::GetCapabilities, GetCapabilities
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
req.alt-api: IStiDevice.GetCapabilities
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

# IStiDevice::GetCapabilities method



## -description
The <b>IStiDevice::GetCapabilities</b> method returns a still image device's capabilities.



## -syntax

````
HRESULT GetCapabilities(
  [in, out] PSTI_DEV_CAPS pDevCaps
);
````


## -parameters

### -param pDevCaps [in, out]

Caller-supplied pointer to an empty <a href="image.sti_dev_caps">STI_DEV_CAPS</a> structure.


## -returns
If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.


## -remarks
The <b>IStiDevice::GetCapabilities</b> method returns device capability flags in the caller-supplied <a href="image.sti_dev_caps">STI_DEV_CAPS</a> structure.

Before calling <b>IStiDevice::GetCapabilities</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="image.istillimage_createdevice">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.


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