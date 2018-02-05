---
UID : NS:dispmprt._DXGK_DISPLAY_OWNERSHIP_FLAGS
title : "_DXGK_DISPLAY_OWNERSHIP_FLAGS"
author : windows-driver-content
description : Structure filled in by OS upon successful completion of the DxgkCbAcquirePostDisplayOwnership2 callback to provide information about the display state a driver is inheriting.
old-location : display\dxgk_display_ownership_flags.htm
old-project : display
ms.assetid : F5CA04FD-5E2A-4C68-97CF-F3D425A958AA
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : dispmprt/PDXGK_DISPLAY_OWNERSHIP_FLAGS, _DXGK_DISPLAY_OWNERSHIP_FLAGS, DXGK_DISPLAY_OWNERSHIP_FLAGS structure [Display Devices], dispmprt/DXGK_DISPLAY_OWNERSHIP_FLAGS, DXGK_DISPLAY_OWNERSHIP_FLAGS, PDXGK_DISPLAY_OWNERSHIP_FLAGS, PDXGK_DISPLAY_OWNERSHIP_FLAGS structure pointer [Display Devices], *PDXGK_DISPLAY_OWNERSHIP_FLAGS, display.dxgk_display_ownership_flags
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : dispmprt.h
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DXGK_DISPLAY_OWNERSHIP_FLAGS, *PDXGK_DISPLAY_OWNERSHIP_FLAGS
---

# _DXGK_DISPLAY_OWNERSHIP_FLAGS structure
Structure filled in by OS upon successful completion of the DxgkCbAcquirePostDisplayOwnership2 callback to provide information about the display state a driver is inheriting.

## Syntax
````
typedef struct _DXGK_DISPLAY_OWNERSHIP_FLAGS {
  union {
    struct {
      DXGK_FRAMEBUFFER_STATE FrameBufferState  :4;
    };
    UINT Value;
  };
} DXGK_DISPLAY_OWNERSHIP_FLAGS, *PDXGK_DISPLAY_OWNERSHIP_FLAGS;
````

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | dispmprt.h |