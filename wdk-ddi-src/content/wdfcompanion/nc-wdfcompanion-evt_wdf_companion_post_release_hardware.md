---
UID: NC:wdfcompanion.EVT_WDF_COMPANION_POST_RELEASE_HARDWARE
title: EVT_WDF_COMPANION_POST_RELEASE_HARDWARE
author: windows-driver-content
description: For internal use only.
old-location: wdf\evt_wdf_companion_post_release_hardware.htm
old-project: wdf
ms.assetid: ebba5344-dc3a-443f-a080-991dd784eb54
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: EVT_WDF_COMPANION_POST_RELEASE_HARDWARE, EVT_WDF_COMPANION_POST_RELEASE_HARDWARE callback function, wdf.evt_wdf_companion_post_release_hardware, wdfcompanion/EVT_WDF_COMPANION_POST_RELEASE_HARDWARE
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wdfcompanion.h
api_name:
-	EVT_WDF_COMPANION_POST_RELEASE_HARDWARE
product: Windows
targetos: Windows
req.typenames: WDF_COMMON_BUFFER_CONFIG, *PWDF_COMMON_BUFFER_CONFIG
req.product: Windows 10 or later.
---


# EVT_WDF_COMPANION_POST_RELEASE_HARDWARE callback function
For internal use only.

## Syntax

```
EVT_WDF_COMPANION_POST_RELEASE_HARDWARE EvtWdfCompanionPostReleaseHardware;

NTSTATUS EvtWdfCompanionPostReleaseHardware(
  WDFCOMPANION Companion,
  WDFCMRESLIST ResourcesTranslated
)
{...}
```

## Parameters

`Companion`



`ResourcesTranslated`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Minimum UMDF version** | 2.23 |
| **Header** | wdfcompanion.h |
| **IRQL** | PASSIVE_LEVEL |