---
UID: NS:d3dkmthk._D3DKMT_DISPLAYMODELIST
title: "_D3DKMT_DISPLAYMODELIST"
author: windows-driver-content
description: Describes a list of display modes.
old-location: display\d3dkmt_displaymodelist.htm
old-project: display
ms.assetid: 2eb99f42-3639-4327-a880-47e18d1da71d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dkmt_displaymodelist, _D3DKMT_DISPLAYMODELIST, D3DKMT_DISPLAYMODELIST structure [Display Devices], D3DKMT_DISPLAYMODELIST, d3dkmthk/D3DKMT_DISPLAYMODELIST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dkmthk.h
apiname:
-	D3DKMT_DISPLAYMODELIST
product: Windows
targetos: Windows
req.typenames: D3DKMT_DISPLAYMODELIST
---

# _D3DKMT_DISPLAYMODELIST structure
Describes a list of display modes.

## Syntax
````
typedef struct _D3DKMT_DISPLAYMODELIST {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  UINT                           ModeCount;
  D3DKMT_DISPLAYMODE             pModeList[];
} D3DKMT_DISPLAYMODELIST;
````

## Members


`ModeCount`

[in/out] The number of display modes in the array that <b>pModeList</b> specifies.

`pModeList`

[out] An array of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_displaymode.md">D3DKMT_DISPLAYMODE</a> structures that represent the list of display modes.

`VidPnSourceId`

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the display modes apply to.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |