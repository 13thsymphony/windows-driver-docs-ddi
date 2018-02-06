---
UID: NS:d3dkmddi._DXGK_MONITORLINKINFO
title: "_DXGK_MONITORLINKINFO"
author: windows-driver-content
description: This structure was defined in WDDM 2.1, however the usage hints and capabilities structure definitions were nested within DXGK_MONITORLINKINFO.
old-location: display\dxgk_monitorlinkinfo.htm
old-project: display
ms.assetid: 4A22CC69-F529-4D0B-BF00-877468E29429
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PDXGK_MONITORLINKINFO, _DXGK_MONITORLINKINFO, d3dkmddi/PDXGK_MONITORLINKINFO, d3dkmddi/DXGK_MONITORLINKINFO, display.dxgk_monitorlinkinfo, DXGK_MONITORLINKINFO, PDXGK_MONITORLINKINFO structure pointer [Display Devices], DXGK_MONITORLINKINFO structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_MONITORLINKINFO
product: Windows
targetos: Windows
req.typenames: DXGK_MONITORLINKINFO
---

# _DXGK_MONITORLINKINFO structure
This structure was defined in WDDM 2.1, however the usage hints and capabilities structure definitions were nested within DXGK_MONITORLINKINFO.  In order to allow the same capabilities structure to be reused in DXGK_QUERYINTEGRATEDDISPLAYOUT, the nested definitions have been extracted into their own structures.

## Syntax
````
typedef struct _DXGK_MONITORLINKINFO {
  DXGK_MONITORLINKINFO_USAGEHINTS   UsageHints;
  DXGK_MONITORLINKINFO_CAPABILITIES Capabilities;
} DXGK_MONITORLINKINFO, *PDXGK_MONITORLINKINFO;
````

## Members


`Capabilities`

Flags which describe the capabilities for driving the monitor.

`UsageHints`

Hints to the driver on the intended usage of the display device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmddi.h |