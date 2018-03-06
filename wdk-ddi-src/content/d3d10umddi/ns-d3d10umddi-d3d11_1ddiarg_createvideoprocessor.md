---
UID: NS:d3d10umddi.D3D11_1DDIARG_CREATEVIDEOPROCESSOR
title: D3D11_1DDIARG_CREATEVIDEOPROCESSOR
author: windows-driver-content
description: Specifies the attributes of a video processor object.
old-location: display\d3d11_1ddiarg_createvideoprocessor.htm
old-project: display
ms.assetid: 957cfebe-4cd9-4a35-822e-ebde4cd9e84c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDIARG_CREATEVIDEOPROCESSOR, D3D11_1DDIARG_CREATEVIDEOPROCESSOR structure [Display Devices], d3d10umddi/D3D11_1DDIARG_CREATEVIDEOPROCESSOR, display.d3d11_1ddiarg_createvideoprocessor
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
-	D3D11_1DDIARG_CREATEVIDEOPROCESSOR
product: Windows
targetos: Windows
req.typenames: D3D11_1DDIARG_CREATEVIDEOPROCESSOR
---

# D3D11_1DDIARG_CREATEVIDEOPROCESSOR structure
Specifies the attributes of a video processor object.

## Syntax
````
typedef struct D3D11_1DDIARG_CREATEVIDEOPROCESSOR {
  D3D11_1DDI_HVIDEOPROCESSORENUM hVideoProcessorEnum;
  UINT                           RateConversionCapsIndex;
} D3D11_1DDIARG_CREATEVIDEOPROCESSOR;
````

## Members


`hVideoProcessorEnum`

A handle to a video processor enumeration object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum.md">CreateVideoProcessorEnum</a> function.

`RateConversionCapsIndex`

Specifies the frame-rate conversion capabilities for the video processor. The value is a zero-based index that corresponds to the <i>RateConversionIndex</i> parameter of the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorrateconversioncaps.md">GetVideoProcessorRateConversionCaps</a> method.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorrateconversioncaps.md">GetVideoProcessorRateConversionCaps</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum.md">CreateVideoProcessorEnum</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDIARG_CREATEVIDEOPROCESSOR structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>