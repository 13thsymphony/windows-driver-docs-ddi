---
UID : NS:d3dkmddi._DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL
title : _DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL
author : windows-driver-content
description : DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL is used as part of an operation to fill an allocation with a pattern.
old-location : display\dxgk_buildpagingbuffer_fillvirtual.htm
old-project : display
ms.assetid : 373065F6-C754-4517-905E-86A974866120
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL, DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmddi.h
req.include-header : D3dkmddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL
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
req.typenames : DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL
---

# _DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL structure
<b>DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL</b> is used as part of an operation to fill an allocation with a pattern.

## Syntax
````
typedef struct _DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL {
  HANDLE                 hAllocation;
  UINT64                 AllocationOffsetInBytes;
  UINT64                 FillSizeInBytes;
  UINT                   FillPattern;
  D3DGPU_VIRTUAL_ADDRESS DestinationVirtualAddress;
} DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL;
````

## Members

        
            `AllocationOffsetInBytes`

            The offset, in bytes, from the start of the allocation being filled.
        
            `DestinationVirtualAddress`

            The virtual address of the destination in the context of the paging process.
        
            `FillPattern`

            The byte pattern to fill with.
        
            `FillSizeInBytes`

            The number of bytes to fill.
        
            `hAllocation`

            The kernel mode driver handle of the allocation being filled. The handle is returned from <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>. The allocation properties are needed in order to detect if the allocation is swizzled.


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
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_buildpagingbuffer.md">DXGKARG_BUILDPAGINGBUFFER</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>