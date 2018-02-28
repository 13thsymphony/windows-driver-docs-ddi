---
UID: NS:d3dkmddi._DXGK_CONTEXTINFO_CAPS
title: "_DXGK_CONTEXTINFO_CAPS"
author: windows-driver-content
description: DXGK_CONTEXTINFO_CAPS is used to describe the capabilities supported by a driver.
old-location: display\dxgk_contextinfo_caps.htm
old-project: display
ms.assetid: AC65F790-981F-4B50-BB9E-84F79D8F6C4F
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGK_CONTEXTINFO_CAPS, DXGK_CONTEXTINFO_CAPS structure [Display Devices], _DXGK_CONTEXTINFO_CAPS, d3dkmddi/DXGK_CONTEXTINFO_CAPS, display.dxgk_contextinfo_caps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dkmddi.h
api_name:
-	DXGK_CONTEXTINFO_CAPS
product: Windows
targetos: Windows
req.typenames: DXGK_CONTEXTINFO_CAPS
---

# _DXGK_CONTEXTINFO_CAPS structure
<b>DXGK_CONTEXTINFO_CAPS</b> is used to describe  the capabilities supported by a driver.

## Syntax
````
typedef struct _DXGK_CONTEXTINFO_CAPS {
  union {
    struct {
      UINT NoPatchingRequired  :1;
      UINT DriverManagesResidency  :1;
      UINT UseIoMmu  :1;
      UINT Reserved  :29;
    };
    UINT   Value;
  };
} DXGK_CONTEXTINFO_CAPS;
````

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |