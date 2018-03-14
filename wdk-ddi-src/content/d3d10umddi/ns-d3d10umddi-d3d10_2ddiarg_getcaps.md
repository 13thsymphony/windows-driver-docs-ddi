---
UID: NS:d3d10umddi.D3D10_2DDIARG_GETCAPS
title: D3D10_2DDIARG_GETCAPS
author: windows-driver-content
description: The D3D10_2DDIARG_GETCAPS structure contains display device capabilities of a particular type.
old-location: display\d3d10_2ddiarg_getcaps.htm
old-project: display
ms.assetid: 3a22464f-4e0b-4b14-bdbf-b34b3abf9780
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D10_2DDIARG_GETCAPS, D3D10_2DDIARG_GETCAPS structure [Display Devices], UMDisplayDriver_Dx11param_Structs_0d9c80db-e29f-4e2f-b697-bcf87f29034c.xml, d3d10umddi/D3D10_2DDIARG_GETCAPS, display.d3d10_2ddiarg_getcaps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D10_2DDIARG_GETCAPS is supported beginning with the Windows 7 operating system.
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
-	D3D10_2DDIARG_GETCAPS
product: Windows
targetos: Windows
req.typenames: D3D10_2DDIARG_GETCAPS
---

# D3D10_2DDIARG_GETCAPS structure
The D3D10_2DDIARG_GETCAPS structure contains display device capabilities of a particular type.

## Syntax
````
typedef struct D3D10_2DDIARG_GETCAPS {
  D3D10_2DDICAPS_TYPE Type;
  VOID                *pInfo;
  VOID                *pData;
  UINT                DataSize;
} D3D10_2DDIARG_GETCAPS;
````

## Members


`DataSize`

[in/out] The size, in bytes, of the memory block at <b>pData</b>.

`pData`

[out] A pointer to a memory block that is filled with capabilities of the type that is specified by the <b>Type</b> member and possibly determined by the condition that is specified in the memory block at <b>pInfo</b>.

`pInfo`

[in] A pointer to a memory block that contains data that specifies the specific condition on which to retrieve the capabilities of the type that is specified by the <b>Type</b> member.

`Type`

[in] The type of capabilities to retrieve. The Microsoft Direct3D runtime can supply one of the values from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_2ddicaps_type.md">D3D10_2DDICAPS_TYPE</a> enumeration, possibly along with information in the memory block that is pointed to by <b>pInfo</b>, to retrieve particular capability data in the memory block at <b>pData</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3D10_2DDIARG_GETCAPS is supported beginning with the Windows 7 operating system. D3D10_2DDIARG_GETCAPS is supported beginning with the Windows 7 operating system. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_2ddicaps_type.md">D3D10_2DDICAPS_TYPE</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_2DDIARG_GETCAPS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>