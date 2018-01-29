---
UID : NS:iddcx.IDARG_IN_ADAPTER_INIT
title : IDARG_IN_ADAPTER_INIT
author : windows-driver-content
description : Initializes an adapter that will be hosted on a WDF device.
old-location : display\idarg_in_adapter_init.htm
old-project : display
ms.assetid : 2db324c8-69b1-4497-b6a7-76047baeca19
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : iddcx/IDARG_IN_ADAPTER_INIT, IDARG_IN_ADAPTER_INIT, display.idarg_in_adapter_init, IDARG_IN_ADAPTER_INIT structure [Display Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : iddcx.h
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
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : 
---

# IDARG_IN_ADAPTER_INIT structure
Initializes an adapter that will be hosted on a WDF device.

## Syntax
````
typedef struct IDARG_IN_ADAPTER_INIT {
  WDFDEVICE              WdfDevice;
  IDDCX_ADAPTER_CAPS*    pCaps;
  PWDF_OBJECT_ATTRIBUTES ObjectAttributes;
} IDARG_IN_ADAPTER_INIT, *IDARG_IN_ADAPTER_INIT;
````

## Members


`ObjectAttributes`

[in][optional] Object attributes that are used to initialize the WDF adapter object.

`pCaps`

[in] A reference  to the capabilities of the adapter.

`WdfDevice`

The WDF device that will be hosting this WDDM adapter object.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | iddcx.h |