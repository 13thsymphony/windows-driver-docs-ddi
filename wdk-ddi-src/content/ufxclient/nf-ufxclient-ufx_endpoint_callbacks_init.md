---
UID : NF:ufxclient.UFX_ENDPOINT_CALLBACKS_INIT
title : UFX_ENDPOINT_CALLBACKS_INIT function
author : windows-driver-content
description : The UFX_ENDPOINT_CALLBACKS_INIT macro initializes the UFX_ENDPOINT_CALLBACKS structure.
old-location : buses\ufx_endpoint_callbacks_init.htm
old-project : usbref
ms.assetid : 10EB0C86-915F-4C24-ADBE-1D8E8DD8ECB6
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : UFX_ENDPOINT_CALLBACKS_INIT function [Buses], ufxclient/UFX_ENDPOINT_CALLBACKS_INIT, buses.ufx_endpoint_callbacks_init, UFX_ENDPOINT_CALLBACKS_INIT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ufxclient.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PUFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT"
req.product : Windows 10 or later.
---


# UFX_ENDPOINT_CALLBACKS_INIT function
The <b>UFX_ENDPOINT_CALLBACKS_INIT</b> macro initializes the <a href="..\ufxclient\ns-ufxclient-_ufx_endpoint_callbacks.md">UFX_ENDPOINT_CALLBACKS</a> structure.<div class="alert"><b>Note</b>  <p class="note">Note that there are currently no endpoint callback functions defined in the <a href="..\ufxclient\ns-ufxclient-_ufx_endpoint_callbacks.md">UFX_ENDPOINT_CALLBACKS</a> structure. 

</div>
<div> </div>

## Syntax

````
FORCEINLINE void UFX_ENDPOINT_CALLBACKS_INIT(
  _Out_ PUFX_DEVICE_CALLBACKS Callbacks
);
````

## Parameters

`Callbacks`

A pointer to the <a href="..\ufxclient\ns-ufxclient-_ufx_endpoint_callbacks.md">UFX_ENDPOINT_CALLBACKS</a> structure.


## Return Value

This function does not return a value.

## Remarks

The <b>UFX_ENDPOINT_CALLBACKS_INIT</b> macro will set all fields of the <a href="..\ufxclient\ns-ufxclient-_ufx_endpoint_callbacks.md">UFX_ENDPOINT_CALLBACKS</a> structure to zero and set the size field appropriately.
<div class="alert"><b>Note</b>  Note that there are currently no endpoint callback functions defined in the <a href="..\ufxclient\ns-ufxclient-_ufx_endpoint_callbacks.md">UFX_ENDPOINT_CALLBACKS</a> structure. </div><div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ufxclient.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |