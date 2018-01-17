---
UID: NC:wdfcompanion.EVT_WDF_COMPANION_POST_D0_EXIT
title: EVT_WDF_COMPANION_POST_D0_EXIT function
author: windows-driver-content
description: For internal use only.
old-location: wdf\evt_wdf_companion_post_d0_exit.htm
old-project: wdf
ms.assetid: 40ccd895-d01f-4057-a5d1-5274e9d9b913
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: EVT_WDF_COMPANION_POST_D0_EXIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcompanion.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.23
req.alt-api: EVT_WDF_COMPANION_POST_D0_EXIT
req.alt-loc: wdfcompanion.h
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
req.typenames: *PWDF_COMMON_BUFFER_CONFIG, WDF_COMMON_BUFFER_CONFIG
req.product: Windows 10 or later.
---

# EVT_WDF_COMPANION_POST_D0_EXIT function



## -description

			For internal use only.



## -syntax

````
EVT_WDF_COMPANION_POST_D0_EXIT EVT_WDF_COMPANION_POST_D0_EXIT;

NTSTATUS EVT_WDF_COMPANION_POST_D0_EXIT(
  _In_ WDFCOMPANION           Companion,
  _In_ WDF_POWER_DEVICE_STATE TargetState
)
{ ... }
````


## -parameters

### -param Companion [in]


### -param TargetState [in]


## -remarks
