---
UID: NS:d3dkmddi._DXGKARG_RELEASESWIZZLINGRANGE
title: "_DXGKARG_RELEASESWIZZLINGRANGE"
author: windows-driver-content
description: The DXGKARG_RELEASESWIZZLINGRANGE structure describes parameters for releasing a swizzling range.
old-location: display\dxgkarg_releaseswizzlingrange.htm
old-project: display
ms.assetid: f7d1af11-c360-4f7f-a47a-cf7a182b2b78
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKARG_RELEASESWIZZLINGRANGE, display.dxgkarg_releaseswizzlingrange, _DXGKARG_RELEASESWIZZLINGRANGE, DmStructs_7ed7a86e-7376-47a8-8198-9c991005fd0a.xml, DXGKARG_RELEASESWIZZLINGRANGE structure [Display Devices], d3dkmddi/DXGKARG_RELEASESWIZZLINGRANGE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARG_RELEASESWIZZLINGRANGE
product: Windows
targetos: Windows
req.typenames: DXGKARG_RELEASESWIZZLINGRANGE
---

# _DXGKARG_RELEASESWIZZLINGRANGE structure
The DXGKARG_RELEASESWIZZLINGRANGE structure describes parameters for releasing a swizzling range.

## Syntax
````
typedef struct _DXGKARG_RELEASESWIZZLINGRANGE {
  HANDLE hAllocation;
  UINT   PrivateDriverData;
  UINT   RangeId;
} DXGKARG_RELEASESWIZZLINGRANGE;
````

## Members


`hAllocation`

[in] A handle to the allocation that the display miniport driver assigns and that is returned through the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function.

`PrivateDriverData`

[in] The 32 bits of private data that the user-mode display driver sent when the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_acquireswizzlingrange.md">DxgkDdiAcquireSwizzlingRange</a> function was called to acquire the swizzling range.

`RangeId`

[in] The zero-based identifier of the swizzling range that the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_releaseswizzlingrange.md">DxgkDdiReleaseSwizzlingRange</a> function releases.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_releaseswizzlingrange.md">DxgkDdiReleaseSwizzlingRange</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_acquireswizzlingrange.md">DxgkDdiAcquireSwizzlingRange</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_RELEASESWIZZLINGRANGE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>