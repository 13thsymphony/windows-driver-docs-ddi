---
UID : NS:iddcx.IDDCX_CURSOR_CAPS
title : IDDCX_CURSOR_CAPS
author : windows-driver-content
description : Gives information about the capabilities of the cursor.
old-location : display\iddcx_cursor_caps.htm
old-project : display
ms.assetid : 3bd92999-07f3-43bb-a826-4fea3e19168a
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : iddcx/IDDCX_CURSOR_CAPS, IDDCX_CURSOR_CAPS, IDDCX_CURSOR_CAPS structure [Display Devices], display.iddcx_cursor_caps
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

# IDDCX_CURSOR_CAPS structure
Gives information about the capabilities of the cursor.

## Syntax
````
typedef struct IDDCX_CURSOR_CAPS {
  UINT                     Size;
  IDDCX_XOR_CURSOR_SUPPORT ColorXorCursorSupport;
  BOOL                     AlphaCursorSupport;
  UINT                     MaxX;
  UINT                     MaxY;
} IDDCX_CURSOR_CAPS, *IDDCX_CURSOR_CAPS;
````

## Members


`AlphaCursorSupport`

Indicates if the adapter supports the 32-bit alpha cursor format. Most cursors are alpha format.

`ColorXorCursorSupport`

Indicates what level of support the driver has for XOR masks in the 32-bit masked color cursor format.
<div class="alert"><b>Note</b>  The OS first converts any monochrome cursor to a color mask cursor.</div><div> </div>

`MaxX`

The maximum width supported for all supported cursor types.

`MaxY`

The maximum height support for all cursor types.

`Size`

Total size of the structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | iddcx.h |