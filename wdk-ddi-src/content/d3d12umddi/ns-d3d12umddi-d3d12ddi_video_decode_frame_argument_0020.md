---
UID : NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020
title : D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020
author : windows-driver-content
description : Contains the decode parameters for the frame.
old-location : display\d3d12ddi_video_decode_frame_parameter.htm
old-project : display
ms.assetid : 5651BDA8-256F-4041-A8BB-E3B30DB1870C
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020, D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3d12umddi.h
req.include-header : D3d12umddi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020
req.alt-loc : D3d12umddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020
---

# D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020 structure
Contains the decode parameters for the frame.

## Syntax
````
typedef struct D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020 {
  D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020 Type;
  VOID                                      *pData;
  UINT                                      Size;
} D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020;
````

## Members

        
            `pData`

            A pointer to the parameter data.
        
            `Size`

            The size, in bytes, of the parameter data specified by the <i>pParameter</i> parameter.
        
            `Type`

            The type of the parameter.  For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_parameter_type_0020.md">D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE</a> enumeration.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |

    ## See Also

        <dl>
<dt>
<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_parameter_type_0020.md">D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_VIDEO_DECODE_FRAME_ARGUMENT_0020 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>