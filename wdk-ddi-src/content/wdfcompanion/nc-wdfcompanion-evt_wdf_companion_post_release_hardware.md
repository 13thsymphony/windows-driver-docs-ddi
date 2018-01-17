---
UID: NC:wdfcompanion.EVT_WDF_COMPANION_POST_RELEASE_HARDWARE
title: EVT_WDF_COMPANION_POST_RELEASE_HARDWARE function
author: windows-driver-content
description: For internal use only.
old-location: wdf\evt_wdf_companion_post_release_hardware.htm
old-project: wdf
ms.assetid: ebba5344-dc3a-443f-a080-991dd784eb54
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: EVT_WDF_COMPANION_POST_RELEASE_HARDWARE
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
req.alt-api: EVT_WDF_COMPANION_POST_RELEASE_HARDWARE
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

# EVT_WDF_COMPANION_POST_RELEASE_HARDWARE function



## -description

			For internal use only.



## -syntax

````
EVT_WDF_COMPANION_POST_RELEASE_HARDWARE EVT_WDF_COMPANION_POST_RELEASE_HARDWARE;

NTSTATUS EVT_WDF_COMPANION_POST_RELEASE_HARDWARE(
  _In_ WDFCOMPANION Companion,
  _In_ WDFCMRESLIST ResourcesTranslated
)
{ ... }
````


## -parameters

### -param Companion [in]


### -param ResourcesTranslated [in]


## -remarks
