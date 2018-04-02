---
UID: NC:video.PMINIPORT_DPC_ROUTINE
title: PMINIPORT_DPC_ROUTINE
author: windows-driver-content
description: The HwVidDpcRoutine function is a miniport driver-implemented callback that is called when a queued DPC gets scheduled.
old-location: display\hwviddpcroutine.htm
old-project: display
ms.assetid: d4b443a2-3665-4e7c-b84a-5388a8fe8681
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HwVidDpcRoutine, HwVidDpcRoutine callback function [Display Devices], PMINIPORT_DPC_ROUTINE, VideoMiniport_Functions_5d605867-89d7-44a9-b08b-c49ffaa90244.xml, display.hwviddpcroutine, video/HwVidDpcRoutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	video.h
api_name:
-	HwVidDpcRoutine
product:
- Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---


# PMINIPORT_DPC_ROUTINE callback function
<i>The HwVidDpcRoutine</i> function is a miniport driver-implemented callback that is called when a queued DPC gets scheduled.

## Syntax

```
PMINIPORT_DPC_ROUTINE PminiportDpcRoutine;

void PminiportDpcRoutine(
  IN PVOID HwDeviceExtension,
  IN PVOID Context
)
{...}
```

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's hardware device extension. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.

`Context`

Contains any miniport driver-supplied data this function may need. <i>Context</i> can be <b>NULL</b> if the DPC implementation does not require additional information.


## Return Value

None

## Remarks

The miniport driver queues this DPC by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff570339">VideoPortQueueDpc</a>.

Because <i>HwVidDpcRoutine </i>is called at DISPATCH_LEVEL, it must not manipulate any pageable code or data. Further, this function must be in nonpaged memory and should complete its operations as quickly as possible.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570339">VideoPortQueueDpc</a>