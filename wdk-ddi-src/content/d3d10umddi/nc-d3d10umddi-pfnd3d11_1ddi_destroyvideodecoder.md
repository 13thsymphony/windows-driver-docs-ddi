---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYVIDEODECODER
title: PFND3D11_1DDI_DESTROYVIDEODECODER
author: windows-driver-content
description: Releases resources for the video decoder object that were created through a call to the CreateVideoDecoder function.
old-location: display\destroyvideodecoder.htm
old-project: display
ms.assetid: 541f4c9b-3193-46a8-9979-74456168988e
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.destroyvideodecoder, pfnDestroyVideoDecoder callback function [Display Devices], pfnDestroyVideoDecoder, PFND3D11_1DDI_DESTROYVIDEODECODER, PFND3D11_1DDI_DESTROYVIDEODECODER, d3d10umddi/pfnDestroyVideoDecoder
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
-	pfnDestroyVideoDecoder
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---


# PFND3D11_1DDI_DESTROYVIDEODECODER callback function
Releases resources for the video decoder object that were created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder.md">CreateVideoDecoder</a> function.

## Syntax

```
PFND3D11_1DDI_DESTROYVIDEODECODER Pfnd3d111DdiDestroyvideodecoder;

void Pfnd3d111DdiDestroyvideodecoder(
   D3D10DDI_HDEVICE,
   D3D11_1DDI_HDECODE
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D11_1DDI_HDECODE`




## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder.md">CreateVideoDecoder</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_DESTROYVIDEODECODER callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>