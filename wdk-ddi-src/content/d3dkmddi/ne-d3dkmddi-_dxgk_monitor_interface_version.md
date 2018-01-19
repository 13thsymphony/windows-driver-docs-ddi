---
UID : NE:d3dkmddi._DXGK_MONITOR_INTERFACE_VERSION
title : _DXGK_MONITOR_INTERFACE_VERSION
author : windows-driver-content
description : Indicates a particular version of the Monitor interface.
old-location : display\dxgk_monitor_interface_version.htm
old-project : display
ms.assetid : 76af0d70-f9bb-4768-9bfd-f2aaeb212db0
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXGK_MONITOR_INTERFACE_VERSION, DXGK_MONITOR_INTERFACE_VERSION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3dkmddi.h
req.include-header : D3dkmddi.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DXGK_MONITOR_INTERFACE_VERSION
req.alt-loc : d3dkmddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : DXGK_MONITOR_INTERFACE_VERSION
---

# _DXGK_MONITOR_INTERFACE_VERSION Enumeration
The <b>DXGK_MONITOR_INTERFACE_VERSION</b> enumeration indicates a particular version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>.

## Syntax
````
typedef enum _DXGK_MONITOR_INTERFACE_VERSION { 
  DXGK_MONITOR_INTERFACE_VERSION_UNINITIALIZED  = 0,
  DXGK_MONITOR_INTERFACE_VERSION_V1             = 1,
  DXGK_MONITOR_INTERFACE_VERSION_V2             = 2
} DXGK_MONITOR_INTERFACE_VERSION;
````

## Constants

<table>

<tr>
<td>DXGK_MONITOR_INTERFACE_VERSION_UNINITIALIZED</td>
<td>Indicates that a variable of type DXGK_MONITOR_INTERFACE_VERSION has not yet been assigned a meaningful value.</td>
</tr>

<tr>
<td>DXGK_MONITOR_INTERFACE_VERSION_V1</td>
<td>Indicates version 1, available in Windows Vista and later versions of the Windows operating systems.</td>
</tr>

<tr>
<td>DXGK_MONITOR_INTERFACE_VERSION_V2</td>
<td>Indicates version 2, available in Windows 7 and later versions of the Windows operating systems.</td>
</tr>
</table>

## Remarks

The <b>Version</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_monitor_interface.md">DXGK_MONITOR_INTERFACE</a> structure is a value from the <b>DXGK_MONITOR_INTERFACE_VERSION</b> enumeration.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |