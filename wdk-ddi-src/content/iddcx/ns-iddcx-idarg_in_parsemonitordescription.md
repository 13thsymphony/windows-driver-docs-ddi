---
UID: NS:iddcx.IDARG_IN_PARSEMONITORDESCRIPTION
title: IDARG_IN_PARSEMONITORDESCRIPTION
author: windows-driver-content
description: Gives information about the monitor description.
old-location: display\idarg_in_parsemonitordescription.htm
old-project: display
ms.assetid: dc3c55e3-ddbe-4f06-b9fb-55696dc07502
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IDARG_IN_PARSEMONITORDESCRIPTION, IDARG_IN_PARSEMONITORDESCRIPTION structure [Display Devices], display.idarg_in_parsemonitordescription, iddcx/IDARG_IN_PARSEMONITORDESCRIPTION
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
-	IDARG_IN_PARSEMONITORDESCRIPTION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_PARSEMONITORDESCRIPTION structure
Gives information about the monitor description.

## Syntax
```
struct IDARG_IN_PARSEMONITORDESCRIPTION {
  IDDCX_MONITOR_DESCRIPTION MonitorDescription;
  UINT                      MonitorModeBufferInputCount;
  IDDCX_MONITOR_MODE        *pMonitorModes;
};
```

## Members


`MonitorDescription`

[in] Monitor description the driver should decode.

`MonitorModeBufferInputCount`

[in] The number of monitor modes the <b>pMonitorModes</b> buffer being passed into the driver can hold. A value of zero indicates that the driver should not copy the monitor mode list into the provided buffer, but should set the output buffer size to the size required.

`pMonitorModes`

[out] Pointer to buffer that the driver should copy the monitor modes to if the value is non-NULL. If value is NULL, then driver should not copy any data and should just set the  <a href="https://msdn.microsoft.com/library/windows/hardware/mt761912">IDARG_OUT_PARSEMONITORDESCRIPTION</a> value <b>MonitorModeBufferOutputCount</b> to indicate the size of buffer required to store the modes.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iddcx.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt761912">IDARG_OUT_PARSEMONITORDESCRIPTION</a>