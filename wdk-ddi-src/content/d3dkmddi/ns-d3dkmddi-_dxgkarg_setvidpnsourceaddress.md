---
UID: NS:d3dkmddi._DXGKARG_SETVIDPNSOURCEADDRESS
title: "_DXGKARG_SETVIDPNSOURCEADDRESS"
author: windows-driver-content
description: The DXGKARG_SETVIDPNSOURCEADDRESS structure contains arguments for the DxgkDdiSetVidPnSourceAddress function.
old-location: display\dxgkarg_setvidpnsourceaddress.htm
old-project: display
ms.assetid: b83736b6-17c5-43b8-9204-d165fe07853b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKARG_SETVIDPNSOURCEADDRESS, DXGKARG_SETVIDPNSOURCEADDRESS structure [Display Devices], DmStructs_f179199a-3747-4086-8e77-5434a3e287a1.xml, _DXGKARG_SETVIDPNSOURCEADDRESS, d3dkmddi/DXGKARG_SETVIDPNSOURCEADDRESS, display.dxgkarg_setvidpnsourceaddress
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
-	DXGKARG_SETVIDPNSOURCEADDRESS
product: Windows
targetos: Windows
req.typenames: DXGKARG_SETVIDPNSOURCEADDRESS
---

# _DXGKARG_SETVIDPNSOURCEADDRESS structure
The DXGKARG_SETVIDPNSOURCEADDRESS structure contains arguments for the <a href="https://msdn.microsoft.com/488c929b-3816-457f-b5c2-c176b93d5546">DxgkDdiSetVidPnSourceAddress</a> function.

## Syntax
````
typedef struct _DXGKARG_SETVIDPNSOURCEADDRESS {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID   VidPnSourceId;
  UINT                             PrimarySegment;
  PHYSICAL_ADDRESS                 PrimaryAddress;
  HANDLE                           hAllocation;
  UINT                             ContextCount;
  HANDLE                           Context[1+D3DDDI_MAX_BROADCAST_CONTEXT];
  DXGK_SETVIDPNSOURCEADDRESS_FLAGS Flags;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
  UINT                             Duration;
#endif 
} DXGKARG_SETVIDPNSOURCEADDRESS;
````

## Members


`VidPnSourceId`

An integer that identifies a video present source on the display adapter.

`PrimarySegment`

The identifier of the segment that contains the source's primary surface.

`PrimaryAddress`

The address, within the segment identified by <i>PrimarySegment</i>, of the source's primary surface.

`hAllocation`

[in] If non-NULL, a handle that the display miniport driver assigned to the allocation and returned from its call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function. The driver must reprogram graphics hardware according to the specific private properties of the allocation, which include but are not limited to pitch size, swizzle format, and so on.

`ContextCount`

[in] The number of contexts in the array that the <b>Context</b> member specifies.

`Context`

[in] An array of handles to the contexts that contributed to a display operation.

`Flags`

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_setvidpnsourceaddress_flags.md">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a> structure that identifies the type of display operation to perform.

`Duration`

The length of time, in units of 100 nanoseconds, between when the current present operation flips to the screen and the next vertical blanking interrupt occurs.

If zero, the refresh rate should be the default rate based on the current mode.

Must be supported by WDDM 1.3 and later drivers. Available starting with Windows 8.1.

`PrimaryData`



`DriverPrivateDataSize`



`pDriverPrivateData`



## Remarks
For display mode-switch operations, the <b>ContextCount</b> member is always set to 0 and the content of the <b>Context</b> array is undefined. When a flip operation is performed, <b>ContextCount</b> is set to the number of contexts that contributed to the flip. If a flip operation is broadcast to three contexts, <b>ContextCount</b> is set to 4 (that is, the original context plus three broadcast contexts). The <b>Context</b> array contains the driver context handles for the contexts that contributed to the flip operation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_setvidpnsourceaddress_flags.md">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a>



<a href="https://msdn.microsoft.com/488c929b-3816-457f-b5c2-c176b93d5546">DxgkDdiSetVidPnSourceAddress</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>