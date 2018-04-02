---
UID: NS:d3dumddi._D3DDDIBOX
title: "_D3DDDIBOX"
author: windows-driver-content
description: Describes the bounds of a volume texture.
old-location: display\d3dddibox.htm
old-project: display
ms.assetid: 3CE49C9F-EFFC-4F43-A939-623B28FD5EFB
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIBOX, D3DDDIBOX structure [Display Devices], _D3DDDIBOX, d3dumddi/D3DDDIBOX, display.d3dddibox
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dumddi.h
api_name:
-	D3DDDIBOX
product: Windows
targetos: Windows
req.typenames: D3DDDIBOX
---

# _D3DDDIBOX structure
Describes the bounds of a volume texture.

## Syntax
```
typedef struct _D3DDDIBOX {
  UINT Left;
  UINT Top;
  UINT Right;
  UINT Bottom;
  UINT Front;
  UINT Back;
} D3DDDIBOX;
```

## Members


`Left`

[in] The position of the left side of the box on the x-axis.

`Top`

[in] The position of the top of the box on the y-axis.

`Right`

[in] The position of the right side of the box on the x-axis.

`Bottom`

[in] The position of the bottom of the box on the y-axis.

`Front`

[in] The position of the front of the box on the z-axis.

`Back`

[in] The position of the back of the box on the z-axis.

## Remarks
The height of the volume equals the value in the <b>Bottom</b> member minus the value in the <b>Top</b> member (that is, height = bottom – top). 

The width of the volume equals the value in the <b>Right</b> member minus the value in the <b>Left</b> member (that is, width = right – left). 

The depth of the volume equals the value in the <b>Back</b> member minus the value in the <b>Front</b> member (that is, depth = back – front).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dumddi.h (include D3dumddi.h) |