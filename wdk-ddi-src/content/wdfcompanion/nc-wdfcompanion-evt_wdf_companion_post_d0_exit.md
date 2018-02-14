---
UID: NC:wdfcompanion.EVT_WDF_COMPANION_POST_D0_EXIT
title: EVT_WDF_COMPANION_POST_D0_EXIT
author: windows-driver-content
description: For internal use only.
old-location: wdf\evt_wdf_companion_post_d0_exit.htm
old-project: wdf
ms.assetid: 40ccd895-d01f-4057-a5d1-5274e9d9b913
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evt_wdf_companion_post_d0_exit, EVT_WDF_COMPANION_POST_D0_EXIT callback function, EVT_WDF_COMPANION_POST_D0_EXIT, EVT_WDF_COMPANION_POST_D0_EXIT, EVT_WDF_COMPANION_POST_D0_EXIT, wdfcompanion/EVT_WDF_COMPANION_POST_D0_EXIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfcompanion.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.23
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wdfcompanion.h
apiname:
-	EVT_WDF_COMPANION_POST_D0_EXIT
product: Windows
targetos: Windows
req.typenames: WDF_COMMON_BUFFER_CONFIG, *PWDF_COMMON_BUFFER_CONFIG
req.product: Windows 10 or later.
---


# EVT_WDF_COMPANION_POST_D0_EXIT function
For internal use only.

## Syntax

```
EVT_WDF_COMPANION_POST_D0_EXIT EvtWdfCompanionPostD0Exit;

NTSTATUS EvtWdfCompanionPostD0Exit(
  WDFCOMPANION Companion,
  WDF_POWER_DEVICE_STATE TargetState
)
{...}
```

## Parameters

`Companion`



`TargetState`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Minimum UMDF version** | 2.23 |
| **Header** | wdfcompanion.h |
| **IRQL** | PASSIVE_LEVEL |