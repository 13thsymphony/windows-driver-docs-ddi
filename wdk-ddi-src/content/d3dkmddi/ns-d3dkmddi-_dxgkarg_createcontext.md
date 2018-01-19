---
UID : NS:d3dkmddi._DXGKARG_CREATECONTEXT
title : _DXGKARG_CREATECONTEXT
author : windows-driver-content
description : The DXGKARG_CREATECONTEXT structure describes parameters to create a device context.
old-location : display\dxgkarg_createcontext.htm
old-project : display
ms.assetid : 94239501-2eeb-479a-851a-14ae665c5887
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXGKARG_CREATECONTEXT, DXGKARG_CREATECONTEXT, *INOUT_PDXGKARG_CREATECONTEXT
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
req.alt-api : DXGKARG_CREATECONTEXT
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
req.typenames : DXGKARG_CREATECONTEXT
---

# _DXGKARG_CREATECONTEXT structure
The DXGKARG_CREATECONTEXT structure describes parameters to create a device context.

## Syntax
````
typedef struct _DXGKARG_CREATECONTEXT {
  HANDLE                  hContext;
  UINT                    NodeOrdinal;
  UINT                    EngineAffinity;
  DXGK_CREATECONTEXTFLAGS Flags;
  VOID                    *pPrivateDriverData;
  UINT                    PrivateDriverDataSize;
  DXGK_CONTEXTINFO        ContextInfo;
} DXGKARG_CREATECONTEXT;
````

## Members

        
            `ContextInfo`

            [out] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_contextinfo.md">DXGK_CONTEXTINFO</a> structure that the display miniport driver populates to describe the device context.
        
            `EngineAffinity`

            [in] The engine within the node that <b>NodeOrdinal</b> specifies that the context is created for.
        
            `Flags`

            [in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_createcontextflags.md">DXGK_CREATECONTEXTFLAGS</a> structure that identifies how to create the context.
        
            `hContext`

            [out] A handle to the context that a display miniport driver returns from a call to its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a> function. This handle represents the context in subsequent calls to the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a>, <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a>, and <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroycontext.md">DxgkDdiDestroyContext</a> functions.
        
            `NodeOrdinal`

            [in] The node that the context is created for.
        
            `pPrivateDriverData`

            [in] A pointer to a block of private data that is passed from the user-mode display driver to the display miniport driver.
        
            `PrivateDriverDataSize`

            [in] The size, in bytes, of the private data that <b>pPrivateDriverData</b> points to.


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
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_contextinfo.md">DXGK_CONTEXTINFO</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_createcontextflags.md">DXGK_CREATECONTEXTFLAGS</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroycontext.md">DxgkDdiDestroyContext</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_CREATECONTEXT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>