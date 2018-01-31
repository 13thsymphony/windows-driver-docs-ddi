---
UID : NS:iddcx.IDARG_IN_SWAPCHAINSETDEVICE
title : IDARG_IN_SWAPCHAINSETDEVICE
author : windows-driver-content
description : Gives information about the device that will process the swap chain.
old-location : display\idarg_in_swapchainsetdevice.htm
old-project : display
ms.assetid : afd52391-5b18-4b86-9d35-2d9ed3e20256
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : IDARG_IN_SWAPCHAINSETDEVICE, display.idarg_in_swapchainsetdevice, IDARG_IN_SWAPCHAINSETDEVICE structure [Display Devices], iddcx/IDARG_IN_SWAPCHAINSETDEVICE
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

# IDARG_IN_SWAPCHAINSETDEVICE structure
Gives information about the device that will process the swap chain.

## Syntax
````
typedef struct IDARG_IN_SWAPCHAINSETDEVICE {
  IDXGIDevice* pDevice;
} IDARG_IN_SWAPCHAINSETDEVICE, *IDARG_IN_SWAPCHAINSETDEVICE;
````

## Members


`pDevice`

The DXGI device used to process swap chain frames.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | iddcx.h |