---
UID: NS:d3dumddi._DXVAHDDDI_DEVICE_DESC
title: "_DXVAHDDDI_DEVICE_DESC"
author: windows-driver-content
description: The DXVAHDDDI_DEVICE_DESC structure describes a decode device.
old-location: display\dxvahdddi_device_desc.htm
old-project: display
ms.assetid: c40f4151-a392-463f-888f-d575e6992062
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXVA2_Structs_ed3bcbea-9cf3-4a81-9134-e667e8121924.xml, DXVAHDDDI_DEVICE_DESC, DXVAHDDDI_DEVICE_DESC structure [Display Devices], _DXVAHDDDI_DEVICE_DESC, d3dumddi/DXVAHDDDI_DEVICE_DESC, display.dxvahdddi_device_desc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_DEVICE_DESC is supported beginning with the Windows 7 operating system.
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
-	DXVAHDDDI_DEVICE_DESC
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_DEVICE_DESC
---

# _DXVAHDDDI_DEVICE_DESC structure
The DXVAHDDDI_DEVICE_DESC structure describes a decode device.

## Syntax
```
typedef struct _DXVAHDDDI_DEVICE_DESC {
  DXVAHDDDI_CONTENT_DESC *pContentDesc;
  DXVAHDDDI_DEVICE_USAGE Usage;
} DXVAHDDDI_DEVICE_DESC;
```

## Members


`pContentDesc`

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563039">DXVAHDDDI_CONTENT_DESC</a> structure that describes how the device decodes content.

`Usage`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563051">DXVAHDDDI_DEVICE_USAGE</a>-typed value that indicates how the decode device plays video.

## Remarks
The driver considers the value in the <b>Usage</b> member and the information to which <b>pContentDesc</b> points to optimize its capabilities.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | DXVAHDDDI_DEVICE_DESC is supported beginning with the Windows 7 operating system. DXVAHDDDI_DEVICE_DESC is supported beginning with the Windows 7 operating system. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563039">DXVAHDDDI_CONTENT_DESC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563051">DXVAHDDDI_DEVICE_USAGE</a>