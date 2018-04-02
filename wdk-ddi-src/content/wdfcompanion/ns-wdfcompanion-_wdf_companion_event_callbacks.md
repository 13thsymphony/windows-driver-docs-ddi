---
UID: NS:wdfcompanion._WDF_COMPANION_EVENT_CALLBACKS
title: "_WDF_COMPANION_EVENT_CALLBACKS"
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdf_companion_event_callbacks.htm
old-project: wdf
ms.assetid: 6a9c5420-1847-4145-aea5-9e9c58d86ea1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_COMPANION_EVENT_CALLBACKS, PWDF_COMPANION_EVENT_CALLBACKS, PWDF_COMPANION_EVENT_CALLBACKS structure pointer, WDF_COMPANION_EVENT_CALLBACKS, WDF_COMPANION_EVENT_CALLBACKS structure, _WDF_COMPANION_EVENT_CALLBACKS, wdf.wdf_companion_event_callbacks, wdfcompanion/PWDF_COMPANION_EVENT_CALLBACKS, wdfcompanion/WDF_COMPANION_EVENT_CALLBACKS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfcompanion.h
api_name:
-	WDF_COMPANION_EVENT_CALLBACKS
product:
- Windows
targetos: Windows
req.typenames: WDF_COMPANION_EVENT_CALLBACKS, *PWDF_COMPANION_EVENT_CALLBACKS
req.product: Windows 10 or later.
---

# _WDF_COMPANION_EVENT_CALLBACKS structure
For internal use only.

## Syntax
```
typedef struct _WDF_COMPANION_EVENT_CALLBACKS {
  ULONG                                   Size;
  PFN_WDF_COMPANION_PRE_D0_ENTRY          EvtCompanionPreD0Entry;
  PFN_WDF_COMPANION_POST_D0_EXIT          EvtCompanionPostD0Exit;
  PFN_WDF_COMPANION_PRE_PREPARE_HARDWARE  EvtCompanionPrePrepareHardware;
  PFN_WDF_COMPANION_POST_RELEASE_HARDWARE EvtCompanionPostReleaseHardware;
} WDF_COMPANION_EVENT_CALLBACKS, *PWDF_COMPANION_EVENT_CALLBACKS;
```

## Members


`Size`



`EvtCompanionPreD0Entry`



`EvtCompanionPostD0Exit`



`EvtCompanionPrePrepareHardware`



`EvtCompanionPostReleaseHardware`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum UMDF version** | 2.23 |
| **Header** | wdfcompanion.h |