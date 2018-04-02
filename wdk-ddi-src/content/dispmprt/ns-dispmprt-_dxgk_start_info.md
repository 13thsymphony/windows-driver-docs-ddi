---
UID: NS:dispmprt._DXGK_START_INFO
title: "_DXGK_START_INFO"
author: windows-driver-content
description: The DXGK_START_INFO structure holds information that is needed by the display miniport driver's DxgkDdiStartDevice function.
old-location: display\dxgk_start_info.htm
old-project: display
ms.assetid: 4d28bc79-5145-48a0-99e8-3f81b2ec4a05
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDXGK_START_INFO, DXGK_START_INFO, DXGK_START_INFO structure [Display Devices], DmStructs_c2f6faad-cd05-43ea-ab58-b296bc130e09.xml, PDXGK_START_INFO, PDXGK_START_INFO structure pointer [Display Devices], _DXGK_START_INFO, display.dxgk_start_info, dispmprt/DXGK_START_INFO, dispmprt/PDXGK_START_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dispmprt.h
api_name:
-	DXGK_START_INFO
product:
- Windows
targetos: Windows
req.typenames: DXGK_START_INFO, *PDXGK_START_INFO
---

# _DXGK_START_INFO structure
The DXGK_START_INFO structure holds information that is needed by the display miniport driver's <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a> function.

## Syntax
```
typedef struct _DXGK_START_INFO {
  ULONG RequiredDmaQueueEntry;
  GUID  AdapterGuid;
  LUID  AdapterLuid;
} *PDXGK_START_INFO, DXGK_START_INFO;
```

## Members


`RequiredDmaQueueEntry`

The number of DMA buffers that the display miniport driver (or the display adapter) must be able to hold in a queue. The display miniport driver must preallocate all resources required to accommodate this number of DMA buffers.

`AdapterGuid`

A GUID that will serve as an identifier for the adapter being started.

`AdapterLuid`

Available starting with Windows 8.

A locally unique identifier (LUID) that will serve as an identifier for the adapter being started.

## Remarks
The DirectX graphics kernel subsystem submits DMA buffers to the display miniport driver by calling <a href="https://msdn.microsoft.com/de1925ab-e444-4cf6-acd9-8fdab26afcec">DxgkDdiSubmitCommand</a>.

The <i>DxgkStartInfo</i> parameter of the <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a> function is a pointer to a DXGK_START_INFO structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | dispmprt.h (include Dispmprt.h) |