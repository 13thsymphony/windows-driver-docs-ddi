---
UID: NS:d3dumddi._DXVAHDDDI_CONTENT_DESC
title: "_DXVAHDDDI_CONTENT_DESC"
author: windows-driver-content
description: The DXVAHDDDI_CONTENT_DESC structure describes the video content that a decode device processes.
old-location: display\dxvahdddi_content_desc.htm
old-project: display
ms.assetid: 635a4a47-11b8-4d78-871e-21ee438880df
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXVA2_Structs_8b90044d-bce5-49b0-b6ff-be34ab09a62e.xml, DXVAHDDDI_CONTENT_DESC, DXVAHDDDI_CONTENT_DESC structure [Display Devices], _DXVAHDDDI_CONTENT_DESC, d3dumddi/DXVAHDDDI_CONTENT_DESC, display.dxvahdddi_content_desc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_CONTENT_DESC is supported beginning with the Windows 7 operating system.
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
-	d3dumddi.h
api_name:
-	DXVAHDDDI_CONTENT_DESC
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_CONTENT_DESC
---

# _DXVAHDDDI_CONTENT_DESC structure
The DXVAHDDDI_CONTENT_DESC structure describes the video content that a decode device processes.

## Syntax
```
typedef struct _DXVAHDDDI_CONTENT_DESC {
  DXVAHDDDI_FRAME_FORMAT InputFrameFormat;
  DXVAHDDDI_RATIONAL     InputFrameRate;
  UINT                   InputWidth;
  UINT                   InputHeight;
  DXVAHDDDI_RATIONAL     OutputFrameRate;
  UINT                   OutputWidth;
  UINT                   OutputHeight;
} DXVAHDDDI_CONTENT_DESC;
```

## Members


`InputFrameFormat`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563056">DXVAHDDDI_FRAME_FORMAT</a>-typed value that indicates the frame format of the input video stream.

`InputFrameRate`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563064">DXVAHDDDI_RATIONAL</a> structure that specifies a fractional value that represents the frame rate of the input video stream.

`InputWidth`

[in] The width, in pixels, of the input video stream.

`InputHeight`

[in] The height, in pixels, of the input video stream.

`OutputFrameRate`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563064">DXVAHDDDI_RATIONAL</a> structure that specifies a fractional value that represents the frame rate of the output.

`OutputWidth`

[in] The width, in pixels, of the output video stream.

`OutputHeight`

[in] The height, in pixels, of the output video stream.

## Remarks
The driver can use the information in the members of DXVAHDDDI_CONTENT_DESC to optimize its capabilities. For example, the driver might not require to expose costly capabilities for high-definition content and the de-interlacing capability for progressive content.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | DXVAHDDDI_CONTENT_DESC is supported beginning with the Windows 7 operating system. DXVAHDDDI_CONTENT_DESC is supported beginning with the Windows 7 operating system. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563056">DXVAHDDDI_FRAME_FORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563064">DXVAHDDDI_RATIONAL</a>