---
UID: NS:dispmprt._DXGK_CHILD_CAPABILITIES
title: "_DXGK_CHILD_CAPABILITIES"
author: windows-driver-content
description: The DXGK_CHILD_CAPABILITIES structure contains information about the capabilities of an individual child device of a display adapter.
old-location: display\dxgk_child_capabilities.htm
old-project: display
ms.assetid: 6ab6a505-ad02-4dce-8061-bba13081208a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDXGK_CHILD_CAPABILITIES, DXGK_CHILD_CAPABILITIES, DXGK_CHILD_CAPABILITIES structure [Display Devices], DmStructs_886366a4-949a-4171-abcf-e318df848285.xml, PDXGK_CHILD_CAPABILITIES, PDXGK_CHILD_CAPABILITIES structure pointer [Display Devices], _DXGK_CHILD_CAPABILITIES, display.dxgk_child_capabilities, dispmprt/DXGK_CHILD_CAPABILITIES, dispmprt/PDXGK_CHILD_CAPABILITIES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
-	dispmprt.h
api_name:
-	DXGK_CHILD_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: DXGK_CHILD_CAPABILITIES, *PDXGK_CHILD_CAPABILITIES
---

# _DXGK_CHILD_CAPABILITIES structure
The DXGK_CHILD_CAPABILITIES structure contains information about the capabilities of an individual child device of a display adapter.

## Syntax
```
typedef struct _DXGK_CHILD_CAPABILITIES {
  union {
    DXGK_INTEGRATED_DISPLAY_CHILD  IntegratedDisplayChild;
    DXGK_VIDEO_OUTPUT_CAPABILITIES VideoOutput;
    struct {
      UINT MustBeZero;
    } Other;
  } Type;
  DXGK_CHILD_DEVICE_HPD_AWARENESS HpdAwareness;
} DXGK_CHILD_CAPABILITIES, *PDXGK_CHILD_CAPABILITIES;
```

## Members


`Type`

A union that can contain either video output information or other information in the following members. 
     



#### VideoOutput

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562070">DXGK_VIDEO_OUTPUT_CAPABILITIES</a> structure that contains information about a video output. This member is meaningful only if the child device has type <b>TypeVideoOutput</b>.



#### IntegratedDisplayChild

Returns the integrated display child specific fields of the child capabilities.

`HpdAwareness`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561006">DXGK_CHILD_DEVICE_HPD_AWARENESS</a> enumerator that indicates the child device's level of hot-plug awareness.

## Remarks
The <b>ChildDeviceType</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a> structure is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561008">DXGK_CHILD_DEVICE_TYPE</a> enumerator that indicates type of the child device: <b>TypeVideoOutput</b> or <b>TypeOther</b>.

If a child device is of type <b>TypeVideoOutput</b>, the <b>Type.VideoOutput</b> member of its DXGK_CHILD_DESCRIPTOR structure is a DXGK_VIDEO_OUTPUT_CAPABILITIES structure.

If a child device is of type <b>TypeOther</b>, then <b>Type.Other.MustBeZero</b> must be set to zero.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | dispmprt.h (include Dispmprt.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562070">DXGK_VIDEO_OUTPUT_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>