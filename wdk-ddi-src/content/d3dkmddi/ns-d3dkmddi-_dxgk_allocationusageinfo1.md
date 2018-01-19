---
UID : NS:d3dkmddi._DXGK_ALLOCATIONUSAGEINFO1
title : _DXGK_ALLOCATIONUSAGEINFO1
author : windows-driver-content
description : The DXGK_ALLOCATIONUSAGEINFO1 structure describes how an allocation can be used in DMA buffering.
old-location : display\dxgk_allocationusageinfo1.htm
old-project : display
ms.assetid : 6de3363c-fcf8-4350-acee-b401bb3f82a6
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXGK_ALLOCATIONUSAGEINFO1, DXGK_ALLOCATIONUSAGEINFO1
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmddi.h
req.include-header : D3dkmddi.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DXGK_ALLOCATIONUSAGEINFO1
req.alt-loc : d3dkmddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : DXGK_ALLOCATIONUSAGEINFO1
---

# _DXGK_ALLOCATIONUSAGEINFO1 structure
The DXGK_ALLOCATIONUSAGEINFO1 structure describes how an allocation can be used in DMA buffering.

## Syntax
````
typedef struct _DXGK_ALLOCATIONUSAGEINFO1 {
  union {
    struct {
      UINT PrivateFormat  :1;
      UINT Swizzled  :1;
      UINT MipMap  :1;
      UINT Cube  :1;
      UINT Volume  :1;
      UINT Vertex  :1;
      UINT Index  :1;
      UINT Reserved  :25;
    };
    UINT Value;
  } Flags;
  union {
    D3DDDIFORMAT Format;
    UINT         PrivateFormat;
  };
  UINT SwizzledFormat;
  UINT ByteOffset;
  UINT Width;
  UINT Height;
  UINT Pitch;
  UINT Depth;
  UINT SlicePitch;
} DXGK_ALLOCATIONUSAGEINFO1;
````

## Members

        
            `ByteOffset`

            [out] The offset, in bytes, into the video memory manager's allocation that marks the start of the driver's version of the allocation.
        
            `Depth`

            [out] The depth, in levels, of the allocation (for MIP-mapped and volume textures only).
        
            `Flags`

            [out] A union that contains either a structure (with the first eight members that are described below) or a 32-bit value (in the <b>Value</b> member) that identifies how the allocation is used:
        
            `Height`

            [out] The height, in number of lines, of the allocation.
        
            `Pitch`

            [out] The pitch, in bytes, of the allocation--that is, the distance, in bytes, to the start of the next line.
        
            `SlicePitch`

            [out] The slice pitch, in bytes, from level to level (for cube and volume textures only).
        
            `SwizzledFormat`

            [out] A swizzled format value for the allocation that is private to a specific vendor.
        
            `Width`

            [out] The width, in pixels, of the allocation.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

    ## See Also

        <dl>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationusagehint.md">DXGK_ALLOCATIONUSAGEHINT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_ALLOCATIONUSAGEINFO1 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>