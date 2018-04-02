---
UID: NF:ufxclient.UFX_ENDPOINT_CALLBACKS_INIT
title: UFX_ENDPOINT_CALLBACKS_INIT function
author: windows-driver-content
description: The UFX_ENDPOINT_CALLBACKS_INIT macro initializes the UFX_ENDPOINT_CALLBACKS structure.
old-location: buses\ufx_endpoint_callbacks_init.htm
old-project: usbref
ms.assetid: 10EB0C86-915F-4C24-ADBE-1D8E8DD8ECB6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UFX_ENDPOINT_CALLBACKS_INIT, UFX_ENDPOINT_CALLBACKS_INIT function [Buses], buses.ufx_endpoint_callbacks_init, ufxclient/UFX_ENDPOINT_CALLBACKS_INIT
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ufxclient.h
api_name:
-	UFX_ENDPOINT_CALLBACKS_INIT
product:
- Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---


# UFX_ENDPOINT_CALLBACKS_INIT function
The <b>UFX_ENDPOINT_CALLBACKS_INIT</b> macro initializes the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187975">UFX_ENDPOINT_CALLBACKS</a> structure.<div class="alert"><b>Note</b>  <p class="note">Note that there are currently no endpoint callback functions defined in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187975">UFX_ENDPOINT_CALLBACKS</a> structure. 

</div>
<div> </div>

## Syntax

```
void UFX_ENDPOINT_CALLBACKS_INIT(
  PUFX_ENDPOINT_CALLBACKS Callbacks
);
```

## Parameters

`Callbacks`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187975">UFX_ENDPOINT_CALLBACKS</a> structure.


## Return Value

This function does not return a value.

## Remarks

The <b>UFX_ENDPOINT_CALLBACKS_INIT</b> macro will set all fields of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187975">UFX_ENDPOINT_CALLBACKS</a> structure to zero and set the size field appropriately.

<div class="alert"><b>Note</b>  Note that there are currently no endpoint callback functions defined in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187975">UFX_ENDPOINT_CALLBACKS</a> structure. </div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ufxclient.h |