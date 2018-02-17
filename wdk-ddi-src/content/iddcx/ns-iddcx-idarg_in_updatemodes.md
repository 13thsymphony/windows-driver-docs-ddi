---
UID: NS:iddcx.IDARG_IN_UPDATEMODES
title: IDARG_IN_UPDATEMODES
author: windows-driver-content
description: Gives information about the target modes that will be updated by the driver.
old-location: display\idarg_in_updatemodes.htm
old-project: display
ms.assetid: d18f1da0-0cd0-48bf-bf01-a80887b6b2ac
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IDARG_IN_UPDATEMODES structure [Display Devices], IDARG_IN_UPDATEMODES, display.idarg_in_updatemodes, iddcx/IDARG_IN_UPDATEMODES
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
-	IDARG_IN_UPDATEMODES
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_UPDATEMODES structure
Gives information about the target modes that will be updated by the driver.

## Syntax
````
typedef struct IDARG_IN_UPDATEMODES {
  IDDCX_UPDATE_REASON                              Reason;
  UINT                                             TargetModeCount;
  _Field_size_(TargetModeCount) IDDCX_TARGET_MODE* pTargetModes;
} IDARG_IN_UPDATEMODES, *IDARG_IN_UPDATEMODES;
````

## Members


`pTargetModes`

[in] Pointer to the buffer that the driver should copy the target modes it supports for this monitor into.

`Reason`

Indicates the reason why the driver is updating the modes.

`TargetModeCount`

[in] Number of target modes in the <b>pTargetModes</b> buffer.  This cannot be zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iddcx.h |