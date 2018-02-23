---
UID: NS:iddcx.IDARG_IN_GETDEFAULTDESCRIPTIONMODES
title: IDARG_IN_GETDEFAULTDESCRIPTIONMODES
author: windows-driver-content
description: Gives information about the default monitor modes passed into the driver.
old-location: display\idarg_in_getdefaultdescriptionmodes.htm
old-project: display
ms.assetid: 4d0a1f81-efc0-40aa-9dde-b9cac64afb8b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.idarg_in_getdefaultdescriptionmodes, iddcx/IDARG_IN_GETDEFAULTDESCRIPTIONMODES, IDARG_IN_GETDEFAULTDESCRIPTIONMODES structure [Display Devices], IDARG_IN_GETDEFAULTDESCRIPTIONMODES
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
-	IDARG_IN_GETDEFAULTDESCRIPTIONMODES
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_GETDEFAULTDESCRIPTIONMODES structure
Gives information about the default monitor modes passed into the driver.

## Syntax
````
typedef struct IDARG_IN_GETDEFAULTDESCRIPTIONMODES {
  UINT                                                                     DefaultMonitorModeBufferInputCount;
  _Field_size_opt_(DefaultMonitorModeBufferInputCount) IDDCX_MONITOR_MODE* pDefaultMonitorModes;
} IDARG_IN_GETDEFAULTDESCRIPTIONMODES, *IDARG_IN_GETDEFAULTDESCRIPTIONMODES;
````

## Members


`DefaultMonitorModeBufferInputCount`

[in] The number of monitor modes the <b>pDefaultsMonitorModes</b> buffer being passed into the driver can hold. A value of zero indicates that the driver should not copy the monitor mode list into the provided buffer, but should set the output buffer size to the size required.

`pDefaultMonitorModes`

[out]
                     Pointer to the buffer that the driver should copy the monitor modes to if the value is non-NULL. If value is NULL, then driver should not copy any data and should just set <b>DefaultMonitorModeBufferOutputCount</b> to indicate the size of buffer required to store the modes.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iddcx.h |