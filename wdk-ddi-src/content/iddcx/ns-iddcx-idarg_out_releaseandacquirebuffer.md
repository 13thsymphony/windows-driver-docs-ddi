---
UID : NS:iddcx.IDARG_OUT_RELEASEANDACQUIREBUFFER
title : IDARG_OUT_RELEASEANDACQUIREBUFFER
author : windows-driver-content
description : Gives information about the acquired swap chain buffer.
old-location : display\idarg_out_releaseandacquirebuffer.htm
old-project : display
ms.assetid : d6092c73-b8fb-4f05-97ce-8a6fe67a2b18
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : IDARG_OUT_RELEASEANDACQUIREBUFFER structure [Display Devices], IDARG_OUT_RELEASEANDACQUIREBUFFER, iddcx/IDARG_OUT_RELEASEANDACQUIREBUFFER, display.idarg_out_releaseandacquirebuffer
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

# IDARG_OUT_RELEASEANDACQUIREBUFFER structure
Gives information about the 
             acquired swap chain buffer.

## Syntax
````
typedef struct IDARG_OUT_RELEASEANDACQUIREBUFFER {
  IDDCX_METADATA MetaData;
} IDARG_OUT_RELEASEANDACQUIREBUFFER, *IDARG_OUT_RELEASEANDACQUIREBUFFER;
````

## Members


`MetaData`

[out] Per-frame metadata and frame information.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | iddcx.h |