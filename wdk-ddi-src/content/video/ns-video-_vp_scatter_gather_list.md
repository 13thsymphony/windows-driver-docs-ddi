---
UID: NS:video._VP_SCATTER_GATHER_LIST
title: "_VP_SCATTER_GATHER_LIST"
author: windows-driver-content
description: The VP_SCATTER_GATHER_LIST structure is a collection of one or more scatter/gather elements.
old-location: display\vp_scatter_gather_list.htm
old-project: display
ms.assetid: 485a0e20-0fed-4055-985c-1ff6d5d1c3e9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PVP_SCATTER_GATHER_LIST, PVP_SCATTER_GATHER_LIST, PVP_SCATTER_GATHER_LIST structure pointer [Display Devices], VP_SCATTER_GATHER_LIST, VP_SCATTER_GATHER_LIST structure [Display Devices], Video_Structs_0b59cadd-bf97-44c9-b987-d4dfc5eaaf15.xml, _VP_SCATTER_GATHER_LIST, display.vp_scatter_gather_list, video/PVP_SCATTER_GATHER_LIST, video/VP_SCATTER_GATHER_LIST"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: video.h
req.include-header: Video.h
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	video.h
api_name:
-	VP_SCATTER_GATHER_LIST
product:
- Windows
targetos: Windows
req.typenames: VP_SCATTER_GATHER_LIST, *PVP_SCATTER_GATHER_LIST
req.product: Windows 10 or later.
---

# _VP_SCATTER_GATHER_LIST structure
The VP_SCATTER_GATHER_LIST structure is a collection of one or more scatter/gather elements.

## Syntax
```
typedef struct _VP_SCATTER_GATHER_LIST {
  ULONG                     NumberOfElements;
  ULONG_PTR                 Reserved;
  VP_SCATTER_GATHER_ELEMENT Elements[];
} *PVP_SCATTER_GATHER_LIST, VP_SCATTER_GATHER_LIST;
```

## Members


`NumberOfElements`

Specifies the number of scatter/gather elements in the <b>Elements</b> array member.

`Reserved`

Reserved for system use.

`Elements`

Specifies the number of scatter/gather elements in the <b>Elements</b> array member.

## Remarks
This structure is available in Windows XP and later.

The video port driver aggregates scatter/gather information in a VP_SCATTER_GATHER_LIST structure, passing it to the miniport driver's <a href="https://msdn.microsoft.com/262c4b9b-fdca-4899-a635-fb273bbf4cc8">HwVidExecuteDma</a> callback routine. The miniport driver uses this information when it sets up the video hardware for a DMA transfer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | video.h (include Video.h) |

## See Also

<a href="https://msdn.microsoft.com/262c4b9b-fdca-4899-a635-fb273bbf4cc8">HwVidExecuteDma</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570571">VP_SCATTER_GATHER_ELEMENT</a>