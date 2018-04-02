---
UID: NS:dxva._DXVA_VideoSample
title: "_DXVA_VideoSample"
author: windows-driver-content
description: The DXVA_VideoSample structure is sent by the renderer to the driver to specify the format of a video sample.
old-location: display\dxva_videosample.htm
old-project: display
ms.assetid: 2fab4993-0b34-44ce-a905-5094e6e3ce47
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*LPDXVA_VideoSample, DXVA_VideoSample, DXVA_VideoSample structure [Display Devices], LPDXVA_VideoSample, LPDXVA_VideoSample structure pointer [Display Devices], _DXVA_VideoSample, display.dxva_videosample, dxva/DXVA_VideoSample, dxva/LPDXVA_VideoSample, dxvaref_08c56205-0793-4556-bb9a-e682eb6ca354.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	dxva.h
api_name:
-	DXVA_VideoSample
product:
- Windows
targetos: Windows
req.typenames: DXVA_VideoSample, *LPDXVA_VideoSample
---

# _DXVA_VideoSample structure
The DXVA_VideoSample structure is sent by the renderer to the driver to specify the format of a video sample.

## Syntax
```
typedef struct _DXVA_VideoSample {
  REFERENCE_TIME    rtStart;
  REFERENCE_TIME    rtEnd;
  DXVA_SampleFormat SampleFormat;
  VOID              *lpDDSSrcSurface;
} *LPDXVA_VideoSample, DXVA_VideoSample;
```

## Members


`rtStart`

Specifies the start time of the sample.

`rtEnd`

Specifies the end time of the sample.

`SampleFormat`

Specifies the format of the sample as defined by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564045">DXVA_SampleFormat</a> structure.

`lpDDSSrcSurface`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551733">DD_SURFACE_LOCAL</a> structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | dxva.h (include Dxva.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551733">DD_SURFACE_LOCAL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563912">DXVA_DeinterlaceBlt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564045">DXVA_SampleFormat</a>