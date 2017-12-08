---
UID: NE.wditypes._WDI_STOP_AP_REASON
title: _WDI_STOP_AP_REASON
author: windows-driver-content
description: The WDI_STOP_AP_REASON enumeration defines the reasons an adapter cannot sustain 802.11 Access Point (AP) functionality on any of the PHYs.
old-location: netvista\wdi_stop_ap_reason.htm
old-project: netvista
ms.assetid: F0CACC25-2F7B-431A-8AAB-CBE495178CC1
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WDI_STOP_AP_REASON, WDI_STOP_AP_REASON
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_STOP_AP_REASON
req.alt-loc: wditypes.hpp
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
req.product: Windows 10 or later.
---

# _WDI_STOP_AP_REASON enumeration



## -description
The WDI_STOP_AP_REASON enumeration defines the reasons an adapter cannot sustain 802.11 Access Point (AP) functionality on any of the PHYs.


## -syntax

````
typedef enum _WDI_STOP_AP_REASON { 
  WDI_STOP_AP_REASON_FREQUENCY_NOT_AVAILABLE  = 1,
  WDI_STOP_AP_REASON_CHANNEL_NOT_AVAILABLE    = 2,
  WDI_STOP_AP_REASON_AP_ACTIVE                = 3,
  WDI_STOP_AP_REASON_IHV_START                = 0xFF000000,
  WDI_STOP_AP_REASON_IHV_END                  = 0xFFFFFFFF
} WDI_STOP_AP_REASON;
````


## -enum-fields

### -field WDI_STOP_AP_REASON_FREQUENCY_NOT_AVAILABLE

The adapter determined that no valid operating frequency is available.

### -field WDI_STOP_AP_REASON_CHANNEL_NOT_AVAILABLE

The adapter determined that no operating channel is available.

### -field WDI_STOP_AP_REASON_AP_ACTIVE

The adapter determined that an AP is already active on another 802.11 MAC entity for this physical wireless LAN adapter.

### -field WDI_STOP_AP_REASON_IHV_START

The start value of possible IHV-specified reasons.

### -field WDI_STOP_AP_REASON_IHV_END

The end value of possible IHV-specified reasons.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wditypes.hpp</dt>
</dl>
</td>
</tr>
</table>