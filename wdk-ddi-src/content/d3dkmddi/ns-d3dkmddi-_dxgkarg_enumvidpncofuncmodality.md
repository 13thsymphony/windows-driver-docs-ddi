---
UID: NS:d3dkmddi._DXGKARG_ENUMVIDPNCOFUNCMODALITY
title: "_DXGKARG_ENUMVIDPNCOFUNCMODALITY"
author: windows-driver-content
description: The DXGKARG_ENUMVIDPNCOFUNCMODALITY structure contains arguments for the DxgkDdiEnumVidPnCofuncModality function.
old-location: display\dxgkarg_enumvidpncofuncmodality.htm
old-project: display
ms.assetid: a67c9e20-68bf-45d5-bbf0-d324643b2a5d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKARG_ENUMVIDPNCOFUNCMODALITY, DXGKARG_ENUMVIDPNCOFUNCMODALITY structure [Display Devices], DmStructs_7b6ad975-cf77-450d-9190-f74711cafe71.xml, _DXGKARG_ENUMVIDPNCOFUNCMODALITY, d3dkmddi/DXGKARG_ENUMVIDPNCOFUNCMODALITY, display.dxgkarg_enumvidpncofuncmodality
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_ENUMVIDPNCOFUNCMODALITY
product:
- Windows
targetos: Windows
req.typenames: DXGKARG_ENUMVIDPNCOFUNCMODALITY
---

# _DXGKARG_ENUMVIDPNCOFUNCMODALITY structure
The DXGKARG_ENUMVIDPNCOFUNCMODALITY structure contains arguments for the <a href="https://msdn.microsoft.com/6dda82bd-1a43-4ffe-b398-a9f8cee6d1c1">DxgkDdiEnumVidPnCofuncModality</a> function. The <i>DxgkDdiEnumVidPnCofuncModality</i> function makes the source and target mode sets of a VidPN cofunctional with the VidPN's topology and the modes that have already been pinned.

## Syntax
```
typedef struct _DXGKARG_ENUMVIDPNCOFUNCMODALITY {
  IN D3DKMDT_HVIDPN                        hConstrainingVidPn;
  IN D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE EnumPivotType;
  IN DXGK_ENUM_PIVOT                       EnumPivot;
} DXGKARG_ENUMVIDPNCOFUNCMODALITY;
```

## Members


`hConstrainingVidPn`

A handle to the VidPn object for which the cofunctional modes are being requested.

`EnumPivotType`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff546003">D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE</a> enumerator that supplies the enumeration pivot type.

`EnumPivot`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561064">DXGK_ENUM_PIVOT</a> structure.

## Remarks
If a particular video present source or target is designated as the pivot of the enumeration, then <i>DxgkDdiEnumVidPnCofuncModality</i> must not change the mode set for that source or target.

The D3DKMDT_HVIDPN data type is defined in <i>D3dkmdt.h</i>. The D3DDDI_VIDEO_PRESENT_SOURCE_ID and D3DDDI_VIDEO_PRESENT_TARGET_ID data types are defined in <i>D3dukmdt.h</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546003">D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561064">DXGK_ENUM_PIVOT</a>



<a href="https://msdn.microsoft.com/6dda82bd-1a43-4ffe-b398-a9f8cee6d1c1">DxgkDdiEnumVidPnCofuncModality</a>