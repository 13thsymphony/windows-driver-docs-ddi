---
UID: NF.ufxclient.UFX_ENDPOINT_CALLBACKS_INIT
title: UFX_ENDPOINT_CALLBACKS_INIT function
author: windows-driver-content
description: The UFX_ENDPOINT_CALLBACKS_INIT macro initializes the UFX_ENDPOINT_CALLBACKS structure.
old-location: buses\ufx_endpoint_callbacks_init.htm
old-project: usbref
ms.assetid: 10EB0C86-915F-4C24-ADBE-1D8E8DD8ECB6
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: UFX_ENDPOINT_CALLBACKS_INIT
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
req.alt-api: UFX_ENDPOINT_CALLBACKS_INIT
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

# UFX_ENDPOINT_CALLBACKS_INIT function



## -description
The <b>UFX_ENDPOINT_CALLBACKS_INIT</b> macro initializes the <a href="buses.ufx_endpoint_callbacks">UFX_ENDPOINT_CALLBACKS</a> structure.<div class="alert"><b>Note</b>  <p class="note">Note that there are currently no endpoint callback functions defined in the <a href="buses.ufx_endpoint_callbacks">UFX_ENDPOINT_CALLBACKS</a> structure. 

</div>
<div> </div>




## -syntax

````
FORCEINLINE void UFX_ENDPOINT_CALLBACKS_INIT(
  _Out_ PUFX_DEVICE_CALLBACKS Callbacks
);
````


## -parameters

### -param Callbacks [out]

A pointer to the <a href="buses.ufx_endpoint_callbacks">UFX_ENDPOINT_CALLBACKS</a> structure.


## -returns
This function does not return a value.


## -remarks
The <b>UFX_ENDPOINT_CALLBACKS_INIT</b> macro will set all fields of the <a href="buses.ufx_endpoint_callbacks">UFX_ENDPOINT_CALLBACKS</a> structure to zero and set the size field appropriately.


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