---
UID: NS:d3dkmthk._D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN
title: "_D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN"
author: windows-driver-content
description: The D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN structure identifies a GDI system present-history operation.
old-location: display\d3dkmt_gdimodel_sysmem_presenthistorytoken.htm
old-project: display
ms.assetid: 764e6504-a056-44c4-acf5-1788832a9c70
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN, D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN structure [Display Devices], OpenGL_Structs_2e7ec746-9d7b-43b8-8606-1c92481031a3.xml, _D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN, d3dkmthk/D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN, display.d3dkmt_gdimodel_sysmem_presenthistorytoken
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN is supported beginning with the Windows 7 operating system.
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
-	d3dkmthk.h
api_name:
-	D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN
product: Windows
targetos: Windows
req.typenames: D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN
---

# _D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN structure
The D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN structure identifies a GDI system present-history operation.

## Syntax
```
typedef struct _D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN {
  ULONG64 hlsurf;
  DWORD   dwDirtyFlags;
  UINT64  uiCookie;
} D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN;
```

## Members


`hlsurf`

[in] A 64-bit value that specifies the handle to a logical surface to copy from.

`dwDirtyFlags`

[in] A set of flags in a 32-bit value that identifies the active rectangles (dirty regions) of the GDI surface.

`uiCookie`

[in] A 64-bit value that specifies the handle to a physical surface to copy to.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN is supported beginning with the Windows 7 operating system. D3DKMT_GDIMODEL_SYSMEM_PRESENTHISTORYTOKEN is supported beginning with the Windows 7 operating system. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548188">D3DKMT_PRESENTHISTORYTOKEN</a>