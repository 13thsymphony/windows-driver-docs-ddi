---
UID: NS:pep_x._PEP_LOW_POWER_EPOCH
title: "_PEP_LOW_POWER_EPOCH"
author: windows-driver-content
description: The PEP_LOW_POWER_EPOCH structure is used to provide data for a PEP_DPM_LOW_POWER_EPOCH notification (deprecated).
old-location: kernel\pep_low_power_epoch.htm
old-project: kernel
ms.assetid: 730312DE-5F11-46C8-8298-55AA5756C995
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_LOW_POWER_EPOCH, PEP_LOW_POWER_EPOCH, PEP_LOW_POWER_EPOCH structure [Kernel-Mode Driver Architecture], PPEP_LOW_POWER_EPOCH, PPEP_LOW_POWER_EPOCH structure pointer [Kernel-Mode Driver Architecture], _PEP_LOW_POWER_EPOCH, kernel.pep_low_power_epoch, pepfx/PEP_LOW_POWER_EPOCH, pepfx/PPEP_LOW_POWER_EPOCH"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_LOW_POWER_EPOCH
product:
- Windows
targetos: Windows
req.typenames: PEP_LOW_POWER_EPOCH, *PPEP_LOW_POWER_EPOCH, PEP_LOW_POWER_EPOCH, *PPEP_LOW_POWER_EPOCH
---

# _PEP_LOW_POWER_EPOCH structure
The <b>PEP_LOW_POWER_EPOCH</b> structure is used to provide data for a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186748">PEP_DPM_LOW_POWER_EPOCH</a> notification (deprecated).

## Syntax
```
typedef struct _PEP_LOW_POWER_EPOCH {
  BOOLEAN LowPowerEpoch;
} PEP_LOW_POWER_EPOCH, *PPEP_LOW_POWER_EPOCH;
```

## Members


`LowPowerEpoch`

When <b>TRUE</b>, indicates that the low power epoch is on.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pep_x.h (include Pep_x.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186748">PEP_DPM_LOW_POWER_EPOCH notification</a>