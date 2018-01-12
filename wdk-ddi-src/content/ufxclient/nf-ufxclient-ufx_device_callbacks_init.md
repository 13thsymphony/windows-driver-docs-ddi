---
UID: NF:ufxclient.UFX_DEVICE_CALLBACKS_INIT
title: UFX_DEVICE_CALLBACKS_INIT function
author: windows-driver-content
description: The UFX_DEVICE_CALLBACKS_INIT macro initializes the UFX_DEVICE_CALLBACKS structure.
old-location: buses\ufx_device_callbacks_init.htm
old-project: usbref
ms.assetid: D9E7D359-5FC8-44C8-ACA2-641DEFF17616
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UFX_DEVICE_CALLBACKS_INIT
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
req.alt-api: UFX_DEVICE_CALLBACKS_INIT
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
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# UFX_DEVICE_CALLBACKS_INIT function



## -description
The <b>UFX_DEVICE_CALLBACKS_INIT</b> macro initializes the <a href="..\ufxclient\ns-ufxclient-_ufx_device_callbacks.md">UFX_DEVICE_CALLBACKS</a> structure.



## -syntax

````
FORCEINLINE void UFX_DEVICE_CALLBACKS_INIT(
  _Out_ PUFX_DEVICE_CALLBACKS Callbacks
);
````


## -parameters

### -param Callbacks [out]

A pointer to the <a href="..\ufxclient\ns-ufxclient-_ufx_device_callbacks.md">UFX_DEVICE_CALLBACKS</a> structure.


## -returns
This function does not return a value.


## -remarks
The <b>UFX_DEVICE_CALLBACKS_INIT</b> macro will set all fields of the <a href="..\ufxclient\ns-ufxclient-_ufx_device_callbacks.md">UFX_DEVICE_CALLBACKS</a> structure to zero and set the <b>Size</b> field appropriately.

The client driver uses the <b>UFX_DEVICE_CALLBACKS_INIT</b> macro the initialize the <a href="..\ufxclient\ns-ufxclient-_ufx_device_callbacks.md">UFX_DEVICE_CALLBACKS</a> structure prior to calling <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.


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