---
UID: NS:d3dkmddi._DXGK_MONITORFREQUENCYRANGESET_INTERFACE
title: "_DXGK_MONITORFREQUENCYRANGESET_INTERFACE"
author: windows-driver-content
description: The DXGK_MONITORFREQUENCYRANGESET_INTERFACE structure contains pointers to functions that belong to the Monitor Frequency Range Set interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_monitorfrequencyrangeset_interface.htm
old-project: display
ms.assetid: 4a973ecd-341f-4766-9fed-f56e55f8deae
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGK_MONITORFREQUENCYRANGESET_INTERFACE, DXGK_MONITORFREQUENCYRANGESET_INTERFACE structure [Display Devices], DXGK_MONITORFREQUENCYRANGESET_INTERFACE, _DXGK_MONITORFREQUENCYRANGESET_INTERFACE, DmStructs_7ff19615-df83-4d5e-91c2-8a94a1cfeea3.xml, display.dxgk_monitorfrequencyrangeset_interface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_MONITORFREQUENCYRANGESET_INTERFACE
product: Windows
targetos: Windows
req.typenames: DXGK_MONITORFREQUENCYRANGESET_INTERFACE
---

# _DXGK_MONITORFREQUENCYRANGESET_INTERFACE structure
The DXGK_MONITORFREQUENCYRANGESET_INTERFACE structure contains pointers to functions that belong to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568430">Monitor Frequency Range Set interface</a>, which is implemented by the video present network (VidPN) manager.

## Syntax
````
typedef struct _DXGK_MONITORFREQUENCYRANGESET_INTERFACE {
  DXGKDDI_MONITORFREQUENCYRANGESET_GETNUMFREQUENCYRANGES          pfnGetNumFrequencyRanges;
  DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIREFIRSTFREQUENCYRANGEINFO pfnAcquireFirstFrequencyRangeInfo;
  DXGKDDI_MONITORFREQUENCYRANGESET_ACQUIRENEXTFREQUENCYRANGEINFO  pfnAcquireNextFrequencyRangeInfo;
  DXGKDDI_MONITORFREQUENCYRANGESET_RELEASEFREQUENCYRANGEINFO      pfnReleaseFrequencyRangeInfo;
} DXGK_MONITORFREQUENCYRANGESET_INTERFACE;
````

## Members


`pfnAcquireFirstFrequencyRangeInfo`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_acquirefirstfrequencyrangeinfo.md">pfnAcquireFirstFrequencyRangeInfo</a> function.

`pfnAcquireNextFrequencyRangeInfo`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_acquirenextfrequencyrangeinfo.md">pfnAcquireNextFrequencyRangeInfo</a> function.

`pfnGetNumFrequencyRanges`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_getnumfrequencyranges.md">pfnGetNumFrequencyRanges</a> function.

`pfnReleaseFrequencyRangeInfo`

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_releasefrequencyrangeinfo.md">pfnReleaseFrequencyRangeInfo</a> function.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |