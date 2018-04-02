---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_SETMARKERMODE
title: PFND3DWDDM1_3DDI_SETMARKERMODE
author: windows-driver-content
description: Notifies the user-mode display driver that it should support a type of Event Tracing for Windows (ETW) marker event. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later drivers.
old-location: display\setmarkermode.htm
old-project: display
ms.assetid: 18B13509-7692-4336-937C-264B31A6FB78
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DWDDM1_3DDI_SETMARKERMODE, SetMarkerMode, SetMarkerMode callback function [Display Devices], d3d10umddi/SetMarkerMode, display.setmarkermode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
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
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	SetMarkerMode
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3DWDDM1_3DDI_SETMARKERMODE callback function
Notifies the user-mode display driver that it should support a type of Event Tracing for Windows (ETW) marker event. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later drivers.

## Syntax

```
PFND3DWDDM1_3DDI_SETMARKERMODE Pfnd3dwddm13DdiSetmarkermode;

void Pfnd3dwddm13DdiSetmarkermode(
  D3D10DDI_HDEVICE hDevice,
  D3DWDDM1_3DDI_MARKER_TYPE Type,
  UINT Flags
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`Type`

A value from the <a href="https://msdn.microsoft.com/library/windows/hardware/dn535968">D3DWDDM1_3DDI_MARKER_TYPE</a> enumeration that indicates the type of marker event  that the driver should support.

`Flags`

A <b>UINT</b> value that indicates whether the driver should provide custom info in command buffers. If set to <b>D3DWDDM1_3DDI_SETMARKERMODE_CUSTOMDRIVEREVENTS</b>, the driver should annotate and instrument command buffers with custom event info. Otherwise, the driver should not annotate command buffers.

The annotation can be in the form of a text string in the English-US locale, or in the form of an index value to a location in a string table. For the latter option, the driver must also implement a function that describes the strings that the index values indicate.


## Return Value

Returns <b>S_OK</b> or an appropriate error result if the function does not complete successfully.

## Remarks

Follow these guidelines when you set up profile-type marker events in your user-mode driver, indicated by the <b>D3DWDDM1_3DDI_MARKER_TYPE_PROFILE</b> type:

<ol>
<li>Use lightweight instrumentation that doesn't produce a strong correlation with graphics command boundaries.</li>
<li>The driver must be able to sample the GPU time stamp at the end of the graphics pipeline.</li>
<li>Don't use sampling commands that place a high performance burden on the graphics pipeline, such as wait-for-idle commands. To be able to instrument profile-type marker events, your driver shouldn't have to flush the pipeline or caches.</li>
</ol>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1,WDDM 1.3 and later Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn535968">D3DWDDM1_3DDI_MARKER_TYPE</a>