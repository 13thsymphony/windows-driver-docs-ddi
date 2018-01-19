---
UID : NS:ufxclient._UFX_ENDPOINT_CALLBACKS
title : _UFX_ENDPOINT_CALLBACKS
author : windows-driver-content
description : The UFX_ENDPOINT_CALLBACKS structure is used to define then event callback functions supported by the client driver.
old-location : buses\ufx_endpoint_callbacks.htm
old-project : usbref
ms.assetid : CED05E15-E141-4A6D-A657-CF0DF9FD1200
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _UFX_ENDPOINT_CALLBACKS, UFX_ENDPOINT_CALLBACKS, *PUFX_ENDPOINT_CALLBACKS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ufxclient.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : UFX_ENDPOINT_CALLBACKS
req.alt-loc : ufxclient.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : UFX_ENDPOINT_CALLBACKS, *PUFX_ENDPOINT_CALLBACKS
req.product : Windows 10 or later.
---

# _UFX_ENDPOINT_CALLBACKS structure
The <b>UFX_ENDPOINT_CALLBACKS</b> structure is used to define then event callback functions supported by the client driver.

## Syntax
````
typedef struct _UFX_ENDPOINT_CALLBACKS {
  ULONG Size;
} UFX_ENDPOINT_CALLBACKS, *PUFX_ENDPOINT_CALLBACKS;
````

## Members

        
            `Size`

            The size of the <b>UFX_ENDPOINT_CALLBACKS</b>         structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ufxclient.h |