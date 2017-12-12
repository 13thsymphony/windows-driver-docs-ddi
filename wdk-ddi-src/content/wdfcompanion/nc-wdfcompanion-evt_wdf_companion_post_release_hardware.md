---
UID: NC.wdfcompanion.EVT_WDF_COMPANION_POST_RELEASE_HARDWARE
title: EVT_WDF_COMPANION_POST_RELEASE_HARDWARE
author: windows-driver-content
description: For internal use only.
old-location: wdf\evt_wdf_companion_post_release_hardware.htm
old-project: wdf
ms.assetid: ebba5344-dc3a-443f-a080-991dd784eb54
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _WDF_COMMON_BUFFER_CONFIG, *PWDF_COMMON_BUFFER_CONFIG, WDF_COMMON_BUFFER_CONFIG
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
req.product: Windows 10 or later.
---

# EVT_WDF_COMPANION_POST_RELEASE_HARDWARE callback



## -description

			For internal use only.



## -prototype

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


## -requirements
<table>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.23

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfcompanion.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>