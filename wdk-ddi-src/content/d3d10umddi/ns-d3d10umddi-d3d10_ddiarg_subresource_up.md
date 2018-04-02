---
UID: NS:d3d10umddi.D3D10_DDIARG_SUBRESOURCE_UP
title: D3D10_DDIARG_SUBRESOURCE_UP
author: windows-driver-content
description: The D3D10_DDIARG_SUBRESOURCE_UP structure describes initialization information about a subresource.
old-location: display\d3d10_ddiarg_subresource_up.htm
old-project: display
ms.assetid: 035ce56c-b2a0-4ee0-83ce-4a45f05e5ff4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D10_DDIARG_SUBRESOURCE_UP, D3D10_DDIARG_SUBRESOURCE_UP structure [Display Devices], UMDisplayDriver_Dx10param_Structs_4bc98700-ad44-4b40-9fc2-b40eeae79626.xml, d3d10umddi/D3D10_DDIARG_SUBRESOURCE_UP, display.d3d10_ddiarg_subresource_up
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	d3d10umddi.h
api_name:
-	D3D10_DDIARG_SUBRESOURCE_UP
product: Windows
targetos: Windows
req.typenames: D3D10_DDIARG_SUBRESOURCE_UP
---

# D3D10_DDIARG_SUBRESOURCE_UP structure
The D3D10_DDIARG_SUBRESOURCE_UP structure describes initialization information about a subresource.

## Syntax
```
typedef struct D3D10_DDIARG_SUBRESOURCE_UP {
  VOID *pSysMem;
  UINT SysMemPitch;
  UINT SysMemSlicePitch;
};
```

## Members


`pSysMem`

[in] A pointer to a buffer that contains the contents of the subresource to copy from.

`SysMemPitch`

[in] The pitch, in bytes, of the surface--that is, the distance, in bytes, to the start of the next row.

`SysMemSlicePitch`

[in] The pitch, in bytes, of the depth slice--that is, the distance, in bytes, to the start of the next depth, where a 3-D subresource is composed of width x rows x depth.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a>