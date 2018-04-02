---
UID: NS:iddcx.IDARG_IN_SET_GAMMARAMP
title: IDARG_IN_SET_GAMMARAMP
author: windows-driver-content
description: Gives information about the gamma ramp being set.
old-location: display\idarg_in_set_gammaramp.htm
old-project: display
ms.assetid: 1e14bcaf-1454-4930-a3b8-afc044c4be3f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IDARG_IN_SET_GAMMARAMP, IDARG_IN_SET_GAMMARAMP structure [Display Devices], display.idarg_in_set_gammaramp, iddcx/IDARG_IN_SET_GAMMARAMP
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iddcx.h
api_name:
-	IDARG_IN_SET_GAMMARAMP
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_SET_GAMMARAMP structure
Gives information about the gamma ramp being set.

## Syntax
```
struct IDARG_IN_SET_GAMMARAMP {
  IDDCX_GAMMARAMP_TYPE Type;
  UINT                 GammaRampSizeInBytes;
  PVOID                pGammaRampData;
};
```

## Members


`Type`

[in] The type of gamma ramp being set.

`GammaRampSizeInBytes`

[in] Size in bytes of the provided gamma ramp data.  Set to zero for <a href="https://msdn.microsoft.com/library/windows/hardware/mt761946">IDDCX_GAMMARAMP_TYPE</a>.

`pGammaRampData`

[in] Pointer to gamma ramp data to set.  Set to NULL for <a href="https://msdn.microsoft.com/library/windows/hardware/mt761946">IDDCX_GAMMARAMP_TYPE</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iddcx.h |