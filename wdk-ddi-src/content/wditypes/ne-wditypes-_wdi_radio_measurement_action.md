---
UID: NE.wditypes._WDI_RADIO_MEASUREMENT_ACTION
title: _WDI_RADIO_MEASUREMENT_ACTION
author: windows-driver-content
description: The WDI_RADIO_MEASUREMENT_ACTION enumeration defines the radio measurement actions.
old-location: netvista\wdi_radio_measurement_action.htm
old-project: NetVista
ms.assetid: AA17E666-5934-453D-B55D-98F8616F6369
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WDI_RADIO_MEASUREMENT_ACTION, WDI_RADIO_MEASUREMENT_ACTION
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
req.alt-api: WDI_RADIO_MEASUREMENT_ACTION
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

# _WDI_RADIO_MEASUREMENT_ACTION enumeration



## -description
The WDI_RADIO_MEASUREMENT_ACTION enumeration defines the radio measurement actions.



## -syntax

````
typedef enum _WDI_RADIO_MEASUREMENT_ACTION { 
  WDI_RADIO_MEASUREMENT_ACTION_NEIGHBOR_REPORT_REQUEST   = 4,
  WDI_RADIO_MEASUREMENT_ACTION_NEIGHBOR_REPORT_RESPONSE  = 5
} WDI_RADIO_MEASUREMENT_ACTION;
````


## -enum-fields

### -field WDI_RADIO_MEASUREMENT_ACTION_NEIGHBOR_REPORT_REQUEST

This refers to the neighbor report request action frame sent by the client to the AP.


### -field WDI_RADIO_MEASUREMENT_ACTION_NEIGHBOR_REPORT_RESPONSE

This refers to the neighbor report response action frame from the AP.


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