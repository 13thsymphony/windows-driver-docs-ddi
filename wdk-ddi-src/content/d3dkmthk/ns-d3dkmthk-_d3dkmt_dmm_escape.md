---
UID: NS:d3dkmthk._D3DKMT_DMM_ESCAPE
title: "_D3DKMT_DMM_ESCAPE"
author: windows-driver-content
description: Do not use the D3DKMT_DMM_ESCAPE structure; it is for testing purposes only. The D3DKMT_DMM_ESCAPE structure describes how to control the display mode manager (DMM) in a call to the D3DKMTEscape function.
old-location: display\d3dkmt_dmm_escape.htm
old-project: display
ms.assetid: 9d4a317d-bb0c-47d4-b9f2-e668adc4d0d4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_DMM_ESCAPE, D3DKMT_DMM_ESCAPE structure [Display Devices], OpenGL_Structs_670cf3b6-6c85-4ddc-af88-8891e3f8f6ce.xml, _D3DKMT_DMM_ESCAPE, d3dkmthk/D3DKMT_DMM_ESCAPE, display.d3dkmt_dmm_escape
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	d3dkmthk.h
api_name:
-	D3DKMT_DMM_ESCAPE
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_DMM_ESCAPE
---

# _D3DKMT_DMM_ESCAPE structure
Do not use the D3DKMT_DMM_ESCAPE structure; it is for testing purposes only.
   

The D3DKMT_DMM_ESCAPE structure describes how to control the display mode manager (DMM) in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546940">D3DKMTEscape</a> function.

## Syntax
```
typedef struct _D3DKMT_DMM_ESCAPE {
  D3DKMT_DMMESCAPETYPE Type;
  SIZE_T               ProvidedBufferSize;
  SIZE_T               MinRequiredBufferSize;
  UCHAR                Data[1];
} D3DKMT_DMM_ESCAPE;
```

## Members


`Type`



`ProvidedBufferSize`

actual size of Data[] array, in bytes.

`MinRequiredBufferSize`

minimum required size of Data[] array to contain requested data.

`Data`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546940">D3DKMTEscape</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547970">D3DKMT_ESCAPE</a>