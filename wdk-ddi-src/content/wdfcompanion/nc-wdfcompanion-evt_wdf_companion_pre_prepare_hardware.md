---
UID: NC:wdfcompanion.EVT_WDF_COMPANION_PRE_PREPARE_HARDWARE
title: EVT_WDF_COMPANION_PRE_PREPARE_HARDWARE function
author: windows-driver-content
description: For internal use only.
old-location: wdf\evt_wdf_companion_pre_prepare_hardware.htm
old-project: wdf
ms.assetid: 36076a28-d3f7-4463-b538-59794a18c4f9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: EVT_WDF_COMPANION_PRE_PREPARE_HARDWARE
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
req.alt-api: EVT_WDF_COMPANION_PRE_PREPARE_HARDWARE
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

# EVT_WDF_COMPANION_PRE_PREPARE_HARDWARE function



## -description

			For internal use only.



## -syntax

````
EVT_WDF_COMPANION_PRE_PREPARE_HARDWARE EVT_WDF_COMPANION_PRE_PREPARE_HARDWARE;

NTSTATUS EVT_WDF_COMPANION_PRE_PREPARE_HARDWARE(
  _In_ WDFCOMPANION Companion,
  _In_ WDFCMRESLIST ResourcesRaw,
  _In_ WDFCMRESLIST ResourcesTranslated
)
{ ... }
````


## -parameters

### -param Companion [in]


### -param ResourcesRaw [in]


### -param ResourcesTranslated [in]


## -remarks
