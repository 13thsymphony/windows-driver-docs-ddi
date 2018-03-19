---
UID: NS:d3dkmddi._DXGK_PRESENTMULTIPLANEOVERLAYLIST
title: "_DXGK_PRESENTMULTIPLANEOVERLAYLIST"
author: windows-driver-content
description: Specifies an overlay plane to display in a call to the DxgkDdiPresent function.
old-location: display\dxgk_presentmultiplaneoverlaylist.htm
old-project: display
ms.assetid: 970b3155-9e81-4725-90ee-079339c1d5c5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_PRESENTMULTIPLANEOVERLAYLIST, DXGK_PRESENTMULTIPLANEOVERLAYLIST structure [Display Devices], _DXGK_PRESENTMULTIPLANEOVERLAYLIST, d3dkmddi/DXGK_PRESENTMULTIPLANEOVERLAYLIST, display.dxgk_presentmultiplaneoverlaylist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGK_PRESENTMULTIPLANEOVERLAYLIST
product: Windows
targetos: Windows
req.typenames: DXGK_PRESENTMULTIPLANEOVERLAYLIST
---

# _DXGK_PRESENTMULTIPLANEOVERLAYLIST structure
Specifies an overlay plane to display in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a> function.

## Syntax
````
typedef struct _DXGK_PRESENTMULTIPLANEOVERLAYLIST {
  UINT             LayerIndex;
  BOOL             Enabled;
  HANDLE           hDeviceSpecificAllocation;
  struct {
    UINT SegmentId  :5;
    UINT Reserved  :27;
  };
  PHYSICAL_ADDRESS PhysicalAddress;
} DXGK_PRESENTMULTIPLANEOVERLAYLIST;
````

## Members


`LayerIndex`

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.

`Enabled`

Indicates whether the overlay plane specified by <b>LayerIndex</b> is enabled for display.

`hDeviceSpecificAllocation`

A handle to the device-specific allocation that corresponds to the non device-specific allocation. The display miniport driver must set <b>hDeviceSpecificAllocation</b> to a handle value that it can use to refer to its private tracking structure for the allocation.

`PhysicalAddress`

[in] A <b>PHYSICAL_ADDRESS</b> data type (which is defined as <b>LARGE_INTEGER</b>) that indicates the physical address, within the segment that <b>SegmentId</b> specifies, where the data is read.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a>