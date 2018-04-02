---
UID: NS:d3d10umddi.D3D11_1DDIARG_VIDEODECODERBEGINFRAME
title: D3D11_1DDIARG_VIDEODECODERBEGINFRAME
author: windows-driver-content
description: Specifies a content key in a call to the VideoDecoderBeginFrame function.
old-location: display\d3d11_1ddiarg_videodecoderbeginframe.htm
old-project: display
ms.assetid: e2664aec-dc96-4cf6-921b-ccd4ee6cf04e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D11_1DDIARG_VIDEODECODERBEGINFRAME, D3D11_1DDIARG_VIDEODECODERBEGINFRAME structure [Display Devices], d3d10umddi/D3D11_1DDIARG_VIDEODECODERBEGINFRAME, display.d3d11_1ddiarg_videodecoderbeginframe
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3d10umddi.h
api_name:
-	D3D11_1DDIARG_VIDEODECODERBEGINFRAME
product: Windows
targetos: Windows
req.typenames: D3D11_1DDIARG_VIDEODECODERBEGINFRAME
---

# D3D11_1DDIARG_VIDEODECODERBEGINFRAME structure
Specifies a content key in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451697">VideoDecoderBeginFrame</a>  function.

## Syntax
```
typedef struct D3D11_1DDIARG_VIDEODECODERBEGINFRAME {
  D3D11_1DDI_HVIDEODECODEROUTPUTVIEW hOutputView;
  CONST void                         *pContentKey;
  UINT                               ContentKeySize;
};
```

## Members


`hOutputView`

A handle to the driver's private data for the video decoder output view. This handle was created through a call to the <a href="https://msdn.microsoft.com/619695dc-8525-4200-a0c2-8ce0fb1010ed">CreateVideoProcessorOutputView</a> function.

`pContentKey`

A pointer to a content key that was used to encrypt the video frame data. If no content key was used, set this member to <b>NULL</b>. If the caller provides a content key, the caller must use the session key to encrypt the content key.

For more information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451697">VideoDecoderBeginFrame</a> function.

`ContentKeySize`

The size, in bytes, of the content key that is specified in the <b>pContentKey</b> member.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/619695dc-8525-4200-a0c2-8ce0fb1010ed">CreateVideoProcessorOutputView</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451697">VideoDecoderBeginFrame</a>