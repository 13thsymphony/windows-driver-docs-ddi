---
UID: NS:d3d10umddi.D3D11_1DDIARG_VIDEODECODEREXTENSION
title: D3D11_1DDIARG_VIDEODECODEREXTENSION
author: windows-driver-content
description: Specifies driver-specific data for the extended Microsoft DirectX Video Acceleration (DXVA) decoding function that is provided by a call to the VideoDecoderExtension function.
old-location: display\d3d11_1ddiarg_videodecoderextension.htm
old-project: display
ms.assetid: d11a6be1-f723-47eb-b131-e1b02451e18a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D11_1DDIARG_VIDEODECODEREXTENSION, D3D11_1DDIARG_VIDEODECODEREXTENSION structure [Display Devices], d3d10umddi/D3D11_1DDIARG_VIDEODECODEREXTENSION, display.d3d11_1ddiarg_videodecoderextension
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
-	D3D11_1DDIARG_VIDEODECODEREXTENSION
product: Windows
targetos: Windows
req.typenames: D3D11_1DDIARG_VIDEODECODEREXTENSION
---

# D3D11_1DDIARG_VIDEODECODEREXTENSION structure
Specifies driver-specific data for the extended Microsoft DirectX Video Acceleration (DXVA) decoding function that is provided by a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451699">VideoDecoderExtension</a> function.

## Syntax
```
typedef struct D3D11_1DDIARG_VIDEODECODEREXTENSION {
  UINT               Function;
  void               *pPrivateInputData;
  UINT               PrivateInputDataSize;
  void               *pPrivateOutputData;
  UINT               PrivateOutputDataSize;
  UINT               ResourceCount;
  D3D10DDI_HRESOURCE *pResourceList;
};
```

## Members


`Function`

The function number. This number identifies the operation to perform. Currently no function numbers are defined.

`pPrivateInputData`

A pointer to a buffer that contains input data for the driver.

`PrivateInputDataSize`

The size of the buffer pointed to by <b>pPrivateInputData</b>, in bytes.

`pPrivateOutputData`

A pointer to a buffer that the driver can use to write output data.

`PrivateOutputDataSize`

The size of the buffer pointed to by <b>pPrivateOutputData</b>, in bytes.

`ResourceCount`

The number of elements in the <b>pResourceList</b> array. If <b>pResourceList</b> is <b>NULL</b>, set <b>ResourceCount</b> to zero.

`pResourceList`

A pointer to an array of resource handles. Use this member to pass Direct3D resources to the driver.

## Remarks
The exact meaning of each structure member depends on the value of <b>Function</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451699">VideoDecoderExtension</a>