---
UID : NS:d3dukmdt._D3DDDIARG_CREATERESOURCE2
title : _D3DDDIARG_CREATERESOURCE2
author : windows-driver-content
description : Contains information for creating a resource. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location : display\d3dddiarg_createresource2.htm
old-project : display
ms.assetid : 337874d1-9f9b-429d-a970-60b5d86ac7a2
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _D3DDDIARG_CREATERESOURCE2, D3DDDIARG_CREATERESOURCE2
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dukmdt.h
req.include-header : D3dukmdt.h, D3dkmddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3DDDIARG_CREATERESOURCE2
req.alt-loc : D3dukmdt.h
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
req.typenames : D3DDDIARG_CREATERESOURCE2
---

# _D3DDDIARG_CREATERESOURCE2 structure
Contains information for creating a resource. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.

## Syntax
````
typedef struct _D3DDDIARG_CREATERESOURCE2 {
  D3DDDIFORMAT                   Format;
  D3DDDI_POOL                    Pool;
  D3DDDIMULTISAMPLE_TYPE         MultisampleType;
  UINT                           MultisampleQuality;
  const D3DDDI_SURFACEINFO       *pSurfList;
  UINT                           SurfCount;
  UINT                           MipLevels;
  UINT                           Fvf;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  D3DDDI_RATIONAL                RefreshRate;
  HANDLE                         hResource;
  D3DDDI_RESOURCEFLAGS           Flags;
  D3DDDI_ROTATION                Rotation;
  D3DDDI_RESOURCEFLAGS2          Flags2;
} D3DDDIARG_CREATERESOURCE2;
````

## Members

        
            `Flags`

            [in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_resourceflags.md">D3DDDI_RESOURCEFLAGS</a> structure that identifies the type of resources to create. Note that some of the bit-field flags in <b>D3DDDI_RESOURCEFLAGS</b> require that additional bit-field flags are set as well.
        
            `Flags2`

            [in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_resourceflags2.md">D3DDDI_RESOURCEFLAGS2</a> structure that identifies the type of resources to create. Note that some of the bit-field flags in <b>D3DDDI_RESOURCEFLAGS2</b> require that additional bit-field flags are set as well.
        
            `Format`

            [in] A value of type <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a> that indicates the format of the resources.
        
            `Fvf`

            [in] The FVF format for vertex buffers.
        
            `hResource`

            [in/out] A handle to the resource. On input to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource2.md">CreateResource2</a> function, <b>hResource</b> specifies the handle that the driver should use anytime it calls back into the Microsoft Direct3D runtime. 

The driver generates a unique handle and passes it back to the Direct3D runtime. On output from the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource2.md">CreateResource2</a> function, <b>hResource</b> specifies the handle that the Direct3D runtime should use in subsequent driver calls to identify the resource.
        
            `MipLevels`

            [in] The number of MIP-map levels for the resources.
        
            `MultisampleQuality`

            [in] The quality level of rendering samples in a multiple-sampled surface. The quality level must be a number from 0 through 7 that represents a quality level from 1 through 8, respectively.

Note that even if the surface is not multiple-sampled (that is, if <b>D3DDDIMULTISAMPLE_NONE</b> is specified in <b>MultisampleType</b>) it can still have a quality level that is greater than 1 (which is specified by using a number greater than 0).
        
            `MultisampleType`

            [in] A value of type <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddimultisample_type.md">D3DDDIMULTISAMPLE_TYPE</a> that indicates the number of samples for a multiple-sampled surface. If the surface is not multiple sampled, this value is D3DDDIMULTISAMPLE_NONE (0).
        
            `Pool`

            [in] A value of type <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_pool.md">D3DDDI_POOL</a> that indicates the type of memory pool that the resources are created from.
        
            `pSurfList`

            [in] An array of <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_surfaceinfo.md">D3DDDI_SURFACEINFO</a> structures for the list of surfaces (or other resource types) to create.
        
            `RefreshRate`

            [in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_rational.md">D3DDDI_RATIONAL</a> structure that specifies the refresh rate that the resource is used with. This member is applicable only if the resource is the primary surface and the <b>MatchGdiPrimary</b> bit-field flag is not set in the <b>Flags</b> member. In addition, if the <b>InterlacedRefresh</b> bit-field flag is set in <b>Flags</b>, the user-mode display driver determines that the refresh rate is interleaved (otherwise, progressive).
        
            `Rotation`

            [in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_rotation.md">D3DDDI_ROTATION</a>-typed value that identifies the orientation of the resource. 

For example, consider that the user-mode display driver receives a request for a 480x640 surface to be rotated 90 degrees (<b>D3DDDI_ROTATION_90</b>). The driver should allocate the surface in 640x480 mode for scanning purposes. When rendering to the surface, the driver should perform the 90 degree rotation. 

Orientations other than <b>D3DDDI_ROTATION_IDENTITY</b> are set only when the <b>Primary</b> bit-field flag is also set in the <b>Flags</b> member.
        
            `SurfCount`

            [in] The number of resources in the array that is specified by the <b>pSurfList</b> member.
        
            `VidPnSourceId`

            [in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the primary surface is created on (if the resource contains a primary surface).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dukmdt.h (include D3dukmdt.h, D3dkmddi.h) |

    ## See Also

        <dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource2.md">CreateResource2</a>
</dt>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>
</dt>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddimultisample_type.md">D3DDDIMULTISAMPLE_TYPE</a>
</dt>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_pool.md">D3DDDI_POOL</a>
</dt>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_rational.md">D3DDDI_RATIONAL</a>
</dt>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_resourceflags2.md">D3DDDI_RESOURCEFLAGS2</a>
</dt>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_rotation.md">D3DDDI_ROTATION</a>
</dt>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_surfaceinfo.md">D3DDDI_SURFACEINFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CREATERESOURCE2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>