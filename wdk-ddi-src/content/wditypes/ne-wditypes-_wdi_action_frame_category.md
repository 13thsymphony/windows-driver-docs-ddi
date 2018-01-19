---
UID : NE:wditypes._WDI_ACTION_FRAME_CATEGORY
title : _WDI_ACTION_FRAME_CATEGORY
author : windows-driver-content
description : The WDI_ACTION_FRAME_CATEGORY enumeration defines the action frame categories.
old-location : netvista\wdi_action_frame_category.htm
old-project : netvista
ms.assetid : F2A3D1F0-E6E7-46DC-875A-7F36E6ACBC6D
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _WDI_ACTION_FRAME_CATEGORY, WDI_ACTION_FRAME_CATEGORY
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wditypes.hpp
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : WDI_ACTION_FRAME_CATEGORY
req.alt-loc : wditypes.hpp
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : WDI_ACTION_FRAME_CATEGORY
req.product : Windows 10 or later.
---

# _WDI_ACTION_FRAME_CATEGORY Enumeration
The WDI_ACTION_FRAME_CATEGORY enumeration defines the action frame categories.

## Syntax
````
typedef enum _WDI_ACTION_FRAME_CATEGORY { 
  WDI_ACTION_FRAME_CATEGORY_PUBLIC               = 4,
  WDI_ACTION_FRAME_CATEGORY_RADIO_MEASUREMENT    = 5,
  WDI_ACTION_FRAME_CATEGORY_FAST_BSS_TRANSITION  = 6,
  WDI_ACTION_FRAME_CATEGORY_WNM                  = 10
} WDI_ACTION_FRAME_CATEGORY;
````

## Constants

<table>

<tr>
<td>WDI_ACTION_FRAME_CATEGORY_FAST_BSS_TRANSITION</td>
<td>Specifies a Fast BSS Transition Action frame.  It is used by a currently-associated AP to enable fast BSS transitions over the DS.  Over the DS transitions are not supported in Windows 10.</td>
</tr>

<tr>
<td>WDI_ACTION_FRAME_CATEGORY_PUBLIC</td>
<td>Specifies a Public Action frame.  It is used in:

<ul>
<li>Inter-BSS and AP to unassociated-STA communications</li>
<li>Intra-BSS communication</li>
<li>GAS frames</li>
</ul></td>
</tr>

<tr>
<td>WDI_ACTION_FRAME_CATEGORY_RADIO_MEASUREMENT</td>
<td>Specifies a Radio Measurement Report frame. It is transmitted by a STA requesting another STA to make one or more measurements on one or more channels.</td>
</tr>

<tr>
<td>WDI_ACTION_FRAME_CATEGORY_WNM</td>
<td>Specifies a Wireless Network Management Action frame.  In Windows 10, it is only used for handling BSS Transition Management requests/responses.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wditypes.hpp |