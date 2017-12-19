---
UID: NE.wditypes._WDI_ACTION_FRAME_CATEGORY
title: _WDI_ACTION_FRAME_CATEGORY
author: windows-driver-content
description: The WDI_ACTION_FRAME_CATEGORY enumeration defines the action frame categories.
old-location: netvista\wdi_action_frame_category.htm
old-project: NetVista
ms.assetid: F2A3D1F0-E6E7-46DC-875A-7F36E6ACBC6D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WDI_ACTION_FRAME_CATEGORY, WDI_ACTION_FRAME_CATEGORY
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
req.alt-api: WDI_ACTION_FRAME_CATEGORY
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

# _WDI_ACTION_FRAME_CATEGORY enumeration



## -description
The WDI_ACTION_FRAME_CATEGORY enumeration defines the action frame categories.



## -syntax

````
typedef enum _WDI_ACTION_FRAME_CATEGORY { 
  WDI_ACTION_FRAME_CATEGORY_PUBLIC               = 4,
  WDI_ACTION_FRAME_CATEGORY_RADIO_MEASUREMENT    = 5,
  WDI_ACTION_FRAME_CATEGORY_FAST_BSS_TRANSITION  = 6,
  WDI_ACTION_FRAME_CATEGORY_WNM                  = 10
} WDI_ACTION_FRAME_CATEGORY;
````


## -enum-fields

### -field WDI_ACTION_FRAME_CATEGORY_PUBLIC

Specifies a Public Action frame.  It is used in:

<ul>
<li>Inter-BSS and AP to unassociated-STA communications</li>
<li>Intra-BSS communication</li>
<li>GAS frames</li>
</ul>

### -field WDI_ACTION_FRAME_CATEGORY_RADIO_MEASUREMENT

Specifies a Radio Measurement Report frame. It is transmitted by a STA requesting another STA to make one or more measurements on one or more channels.


### -field WDI_ACTION_FRAME_CATEGORY_FAST_BSS_TRANSITION

Specifies a Fast BSS Transition Action frame.  It is used by a currently-associated AP to enable fast BSS transitions over the DS.  Over the DS transitions are not supported in Windows 10.


### -field WDI_ACTION_FRAME_CATEGORY_WNM

Specifies a Wireless Network Management Action frame.  In Windows 10, it is only used for handling BSS Transition Management requests/responses.


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