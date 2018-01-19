---
UID : NE:dot11wdi._WDI_RX_INDICATION_LEVEL
title : _WDI_RX_INDICATION_LEVEL
author : windows-driver-content
description : The WDI_RX_INDICATION_LEVEL enumeration defines the RX indication levels.
old-location : netvista\wdi_rx_indication_level.htm
old-project : netvista
ms.assetid : 73ad8d04-c245-4a3c-92ff-4729737ede92
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _WDI_RX_INDICATION_LEVEL, WDI_RX_INDICATION_LEVEL
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : dot11wdi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : WDI_RX_INDICATION_LEVEL
req.alt-loc : dot11wdi.h
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
req.typenames : WDI_RX_INDICATION_LEVEL
---

# _WDI_RX_INDICATION_LEVEL Enumeration
The WDI_RX_INDICATION_LEVEL enumeration defines the RX indication levels.

## Syntax
````
typedef enum _WDI_RX_INDICATION_LEVEL { 
  WDI_RX_INDICATION_DISPATCH_GENERAL                           = 0,
  WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC                      = 1,
  WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES                      = 2,
  WDI_RX_INDICATION_PASSIVE                                    = 3,
  WDI_RX_INDICATION_FLAG_RESOURCES                             = 0x80000000,
  WDI_RX_INDICATION_DISPATCH_GENERAL_WITH_LOW_RESOURCES        = WDI_RX_INDICATION_FLAG_RESOURCES | WDI_RX_INDICATION_DISPATCH_GENERAL,
  WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC_WITH_LOW_RESSOURCES  = WDI_RX_INDICATION_FLAG_RESOURCES | WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC,
  WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES_WITH_LOW_RESOURCES   = WDI_RX_INDICATION_FLAG_RESOURCES | WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES,
  WDI_RX_INDICATION_PASSIVE_WITH_LOW_RESOURCES                 = WDI_RX_INDICATION_FLAG_RESOURCES | WDI_RX_INDICATION_PASSIVE
} WDI_RX_INDICATION_LEVEL;
````

## Constants

<table>

<tr>
<td>WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC</td>
<td>Used for the first data indication (<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_rx_inorder_data_ind.md">NdisWdiRxInorderDataIndication</a>) of a DPC.</td>
</tr>

<tr>
<td>WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC_WITH_LOW_RESSOURCES</td>
<td>Bitwise OR of <b>WDI_RX_INDICATION_FLAG_RESOURCES</b> and <b>WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC</b>.</td>
</tr>

<tr>
<td>WDI_RX_INDICATION_DISPATCH_GENERAL</td>
<td>Used for subsequent data indications in a DPC. <b>WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC</b> is used for the first data indication of a DPC.</td>
</tr>

<tr>
<td>WDI_RX_INDICATION_DISPATCH_GENERAL_WITH_LOW_RESOURCES</td>
<td>Bitwise OR of <b>WDI_RX_INDICATION_FLAG_RESOURCES</b> and <b>WDI_RX_INDICATION_DISPATCH_GENERAL</b>.</td>
</tr>

<tr>
<td>WDI_RX_INDICATION_FLAG_RESOURCES</td>
<td>Bitwise OR’d with other enum values to cause RxMgr to set <b>NDIS_RECEIVE_FLAG_RESOURCES</b>.</td>
</tr>

<tr>
<td>WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES</td>
<td>Used when making data indications in the context of <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_resume.md">MiniportWdiRxResume</a>.</td>
</tr>

<tr>
<td>WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES_WITH_LOW_RESOURCES</td>
<td>Bitwise OR of <b>WDI_RX_INDICATION_FLAG_RESOURCES</b> and <b>WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES</b>.</td>
</tr>

<tr>
<td>WDI_RX_INDICATION_PASSIVE</td>
<td>Used when making data indications at passive level.</td>
</tr>

<tr>
<td>WDI_RX_INDICATION_PASSIVE_WITH_LOW_RESOURCES</td>
<td>Bitwise OR of <b>WDI_RX_INDICATION_FLAG_RESOURCES</b> and <b>WDI_RX_INDICATION_PASSIVE</b>.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dot11wdi.h |