---
UID: NS:d3dkmdt._D3DKMDT_MONITOR_DESCRIPTOR
title: "_D3DKMDT_MONITOR_DESCRIPTOR"
author: windows-driver-content
description: The D3DKMDT_MONITOR_DESCRIPTOR structure contains a pointer to a monitor descriptor along with information about the monitor descriptor.
old-location: display\d3dkmdt_monitor_descriptor.htm
old-project: display
ms.assetid: 4bdce35f-adce-4898-8ef5-011a5476065a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMDT_MONITOR_DESCRIPTOR, D3DKMDT_MONITOR_DESCRIPTOR structure [Display Devices], DmStructs_760a75c4-4db4-445e-a63b-7e77b6b69090.xml, _D3DKMDT_MONITOR_DESCRIPTOR, d3dkmdt/D3DKMDT_MONITOR_DESCRIPTOR, display.d3dkmdt_monitor_descriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	D3DKMDT_MONITOR_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: D3DKMDT_MONITOR_DESCRIPTOR
---

# _D3DKMDT_MONITOR_DESCRIPTOR structure
The D3DKMDT_MONITOR_DESCRIPTOR structure contains a pointer to a monitor descriptor along with information about the monitor descriptor.

## Syntax
````
typedef struct _D3DKMDT_MONITOR_DESCRIPTOR {
  D3DKMDT_MONITOR_DESCRIPTOR_ID       Id;
  D3DKMDT_MONITOR_DESCRIPTOR_TYPE     Type;
  SIZE_T                              DataSize;
  VOID                                *pData;
  D3DKMDT_MONITOR_CAPABILITIES_ORIGIN Origin;
} D3DKMDT_MONITOR_DESCRIPTOR;
````

## Members


`Id`

An integer that identifies the monitor descriptor.

`Type`

A value from the <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_monitor_descriptor_type.md">D3DKMDT_MONITOR_DESCRIPTOR_TYPE</a> enumeration that indicates the descriptor type.

`DataSize`

The size, in bytes, of the monitor descriptor.

`pData`

A pointer to the monitor descriptor.

`Origin`

A value of type <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_monitor_capabilities_origin.md">D3DKMDT_MONITOR_CAPABILITIES_ORIGIN</a> that indicates the source of the mode information for the monitor. For example, the mode information could be from a default monitor profile or it could be from an override in an INF file.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

## See Also

<a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_monitor_capabilities_origin.md">D3DKMDT_MONITOR_CAPABILITIES_ORIGIN</a>



<a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_monitor_descriptor_type.md">D3DKMDT_MONITOR_DESCRIPTOR_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568427">Monitor Descriptor Set Interface</a>