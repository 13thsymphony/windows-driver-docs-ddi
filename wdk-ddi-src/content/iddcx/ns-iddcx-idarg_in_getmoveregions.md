---
UID: NS:iddcx.IDARG_IN_GETMOVEREGIONS
title: IDARG_IN_GETMOVEREGIONS
author: windows-driver-content
description: Gives information to the OS about move regions.
old-location: display\idarg_in_getmoveregions.htm
old-project: display
ms.assetid: 8534d6bd-c959-4088-8227-51710fe721cf
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IDARG_IN_GETMOVEREGIONS, display.idarg_in_getmoveregions, IDARG_IN_GETMOVEREGIONS structure [Display Devices], iddcx/IDARG_IN_GETMOVEREGIONS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iddcx.h
apiname:
-	IDARG_IN_GETMOVEREGIONS
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_GETMOVEREGIONS structure
Gives information to the OS about move regions.

## Syntax
````
typedef struct IDARG_IN_GETMOVEREGIONS {
  UINT                                                   MoveRegionInCount;
  _Field_size_full_(MoveRegionInCount) IDDCX_MOVEREGION* pMoveRegions;
} IDARG_IN_GETMOVEREGIONS, *IDARG_IN_GETMOVEREGIONS;
````

## Members


`MoveRegionInCount`

[in] Number of move regions in the <b>pMoveRegions</b> array

`pMoveRegions`

[out] Pointer to the buffer where the OS can copy the move regions.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iddcx.h |