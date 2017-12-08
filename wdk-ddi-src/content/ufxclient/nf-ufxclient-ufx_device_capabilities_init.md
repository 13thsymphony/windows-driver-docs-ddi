---
UID: NF.ufxclient.UFX_DEVICE_CAPABILITIES_INIT
title: UFX_DEVICE_CAPABILITIES_INIT function
author: windows-driver-content
description: The UFX_DEVICE_CAPABILITIES_INIT macro the initializes the UFX_DEVICE_CAPABILITIES structure.
old-location: buses\ufx_device_capabilities_init.htm
old-project: usbref
ms.assetid: 7C55EB8D-1B68-484A-B95A-E0150FBA9AB8
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: UFX_DEVICE_CAPABILITIES_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UFX_DEVICE_CAPABILITIES_INIT
req.alt-loc: ufxclient.h
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

# UFX_DEVICE_CAPABILITIES_INIT function



## -description
The <b>UFX_DEVICE_CAPABILITIES_INIT</b> macro the initializes the <a href="buses.ufx_device_capabilities">UFX_DEVICE_CAPABILITIES</a> structure.


## -syntax

````
void UFX_DEVICE_CAPABILITIES_INIT(
  _Out_ PUFX_DEVICE_CAPABILITIES Capabilities
);
````


## -parameters

### -param Capabilities [out]

Pointer to the <a href="buses.ufx_device_capabilities">UFX_DEVICE_CAPABILITIES</a> structure.

## -returns
This function does not return a value.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ufxclient.h</dt>
</dl>
</td>
</tr>
</table>