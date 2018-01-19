---
UID : NS:video._VP_SCATTER_GATHER_LIST
title : _VP_SCATTER_GATHER_LIST
author : windows-driver-content
description : The VP_SCATTER_GATHER_LIST structure is a collection of one or more scatter/gather elements.
old-location : display\vp_scatter_gather_list.htm
old-project : display
ms.assetid : 485a0e20-0fed-4055-985c-1ff6d5d1c3e9
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _VP_SCATTER_GATHER_LIST, VP_SCATTER_GATHER_LIST, *PVP_SCATTER_GATHER_LIST
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : video.h
req.include-header : Video.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : VP_SCATTER_GATHER_LIST
req.alt-loc : video.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : See Remarks section.
req.typenames : VP_SCATTER_GATHER_LIST, *PVP_SCATTER_GATHER_LIST
req.product : Windows 10 or later.
---

# _VP_SCATTER_GATHER_LIST structure
The VP_SCATTER_GATHER_LIST structure is a collection of one or more scatter/gather elements.

## Syntax
````
typedef struct _VP_SCATTER_GATHER_LIST {
  ULONG                     NumberOfElements;
  ULONG_PTR                 Reserved;
  VP_SCATTER_GATHER_ELEMENT Elements[];
} VP_SCATTER_GATHER_LIST, *PVP_SCATTER_GATHER_LIST;
````

## Members

        
            `Elements`

            Specifies the number of scatter/gather elements in the <b>Elements</b> array member.
        
            `NumberOfElements`

            Specifies the number of scatter/gather elements in the <b>Elements</b> array member.
        
            `Reserved`

            Reserved for system use.

    ## Remarks
        This structure is available in Windows XP and later.

The video port driver aggregates scatter/gather information in a VP_SCATTER_GATHER_LIST structure, passing it to the miniport driver's <a href="..\video\nc-video-pexecute_dma.md">HwVidExecuteDma</a> callback routine. The miniport driver uses this information when it sets up the video hardware for a DMA transfer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | video.h (include Video.h) |

    ## See Also

        <dl>
<dt>
<a href="..\video\ns-video-_vp_scatter_gather_element.md">VP_SCATTER_GATHER_ELEMENT</a>
</dt>
<dt>
<a href="..\video\nc-video-pexecute_dma.md">HwVidExecuteDma</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VP_SCATTER_GATHER_LIST structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>