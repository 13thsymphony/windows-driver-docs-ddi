---
UID : NE:d3d10umddi.D3D11_1DDI_BUS_TYPE
title : D3D11_1DDI_BUS_TYPE
author : windows-driver-content
description : Specifies the type of I/O bus that is used by the graphics adapter.
old-location : display\d3d11_1ddi_bus_type.htm
old-project : display
ms.assetid : 07cf1893-1ced-4bfa-a6f7-ec71345b9f18
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D11_1DDI_BUS_TYPE, D3D11_1DDI_BUS_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3D11_1DDI_BUS_TYPE
req.alt-loc : D3d10umddi.h
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
req.typenames : D3D11_1DDI_BUS_TYPE
---

# D3D11_1DDI_BUS_TYPE Enumeration
Specifies the type of I/O bus that is used by the graphics adapter.

## Syntax
````
typedef enum D3D11_1DDI_BUS_TYPE { 
  D3D11_1DDI_BUS_TYPE_OTHER                                             = 0x00000000,
  D3D11_1DDI_BUS_TYPE_PCI                                               = 0x00000001,
  D3D11_1DDI_BUS_TYPE_PCIX                                              = 0x00000002,
  D3D11_1DDI_BUS_TYPE_PCIEXPRESS                                        = 0x00000003,
  D3D11_1DDI_BUS_TYPE_AGP                                               = 0x00000004,
  D3D11_1DDI_BUS_IMPL_MODIFIER_INSIDE_OF_CHIPSET                        = 0x00010000,
  D3D11_1DDI_BUS_IMPL_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_CHIP           = 0x00020000,
  D3D11_1DDI_BUS_IMPL_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_SOCKET         = 0x00030000,
  D3D11_1DDI_BUS_IMPL_MODIFIER_DAUGHTER_BOARD_CONNECTOR                 = 0x00040000,
  D3D11_1DDI_BUS_IMPL_MODIFIER_DAUGHTER_BOARD_CONNECTOR_INSIDE_OF_NUAE  = 0x00050000,
  D3D11_1DDI_BUS_IMPL_MODIFIER_NON_STANDARD                             = 0x80000000
} D3D11_1DDI_BUS_TYPE;
````

## Constants

<table>

<tr>
<td>D3D11_1DDI_BUS_IMPL_MODIFIER_DAUGHTER_BOARD_CONNECTOR</td>
<td>The graphics adapter is connected to the motherboard through a daughterboard connector.</td>
</tr>

<tr>
<td>D3D11_1DDI_BUS_IMPL_MODIFIER_DAUGHTER_BOARD_CONNECTOR_INSIDE_OF_NUAE</td>
<td>The graphics adapter is connected to the motherboard through a daughterboard connector, and the graphics adapter is inside an enclosure that is not user accessible.</td>
</tr>

<tr>
<td>D3D11_1DDI_BUS_IMPL_MODIFIER_INSIDE_OF_CHIPSET</td>
<td>The implementation for the graphics adapter is in a motherboard chipset's north bridge. This flag implies that data never goes over an expansion bus (such as PCI or AGP) when it is transferred from main memory to the graphics adapter.</td>
</tr>

<tr>
<td>D3D11_1DDI_BUS_IMPL_MODIFIER_NON_STANDARD</td>
<td>One of the D3D11_1DDI_BUS_IMPL_MODIFIER_Xxx flags is set.</td>
</tr>

<tr>
<td>D3D11_1DDI_BUS_IMPL_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_CHIP</td>
<td>Indicates that the graphics adapter is connected to a motherboard chipset's north bridge by tracks on the motherboard, and all of the graphics adapter's chips are soldered to the motherboard. This flag implies that data never goes over an expansion bus (such as PCI or AGP) when it is transferred from main memory to the graphics adapter.</td>
</tr>

<tr>
<td>D3D11_1DDI_BUS_IMPL_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_SOCKET</td>
<td>The graphics adapter is connected to a motherboard chipset's north bridge by tracks on the motherboard, and all of the graphics adapter's chips are connected through sockets to the motherboard.</td>
</tr>

<tr>
<td>D3D11_1DDI_BUS_TYPE_AGP</td>
<td>Accelerated Graphics Port (AGP) bus.</td>
</tr>

<tr>
<td>D3D11_1DDI_BUS_TYPE_OTHER</td>
<td>Indicates a type of bus other than the types listed here.</td>
</tr>

<tr>
<td>D3D11_1DDI_BUS_TYPE_PCI</td>
<td>PCI bus.</td>
</tr>

<tr>
<td>D3D11_1DDI_BUS_TYPE_PCIEXPRESS</td>
<td>PCI Express bus.</td>
</tr>

<tr>
<td>D3D11_1DDI_BUS_TYPE_PCIX</td>
<td>PCI-X bus.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |