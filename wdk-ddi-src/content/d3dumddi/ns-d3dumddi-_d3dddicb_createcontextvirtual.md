---
UID : NS:d3dumddi._D3DDDICB_CREATECONTEXTVIRTUAL
title : "_D3DDDICB_CREATECONTEXTVIRTUAL"
author : windows-driver-content
description : D3DDDICB_CREATECONTEXTVIRTUAL is used with pfnCreateContextVirtualCb to create contexts that support virtual addressing.
old-location : display\d3dddicb_createcontextvirtual.htm
old-project : display
ms.assetid : 451D1CE2-A50D-4E42-BD93-879503EDE4B5
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3dumddi/D3DDDICB_CREATECONTEXTVIRTUAL, display.d3dddicb_createcontextvirtual, _D3DDDICB_CREATECONTEXTVIRTUAL, D3DDDICB_CREATECONTEXTVIRTUAL structure [Display Devices], D3DDDICB_CREATECONTEXTVIRTUAL
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DDDICB_CREATECONTEXTVIRTUAL
---

# _D3DDDICB_CREATECONTEXTVIRTUAL structure
<b>D3DDDICB_CREATECONTEXTVIRTUAL</b> is used with <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcontextvirtualcb.md">pfnCreateContextVirtualCb</a> to create contexts that support virtual addressing.

## Syntax
````
typedef struct _D3DDDICB_CREATECONTEXTVIRTUAL {
  UINT                      NodeOrdinal;
  UINT                      EngineAffinity;
  D3DDDI_CREATECONTEXTFLAGS Flags;
  VOID                      *pPrivateDriverData;
  UINT                      PrivateDriverDataSize;
  HANDLE                    hContext;
} D3DDDICB_CREATECONTEXTVIRTUAL;
````

## Members


`EngineAffinity`

[in] The zero-based index for the engine, within the node that <b>NodeOrdinal</b> specifies, that the context can run in.

`Flags`

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_createcontextflags.md">D3DDDI_CREATECONTEXTFLAGS</a> structure that indicates, in bit-field flags, how to create the context.

`hContext`

[out] A handle to the context that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcontextvirtualcb.md">pfnCreateContextVirtualCb</a> function creates.

`NodeOrdinal`

[in] The zero-based index for the node that the context is scheduled on.

`pPrivateDriverData`

[in] A pointer to private data that is passed to a display miniport driver.

`PrivateDriverDataSize`

[in] The size, in bytes, of the private data that <b>pPrivateDriverData</b> points to.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcontextvirtualcb.md">pfnCreateContextVirtualCb</a>

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_createcontextflags.md">D3DDDI_CREATECONTEXTFLAGS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_CREATECONTEXTVIRTUAL structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>