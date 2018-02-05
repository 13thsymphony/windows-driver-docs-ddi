---
UID : NS:d3dkmthk._D3DKMT_CREATECONTEXTVIRTUAL
title : "_D3DKMT_CREATECONTEXTVIRTUAL"
author : windows-driver-content
description : D3DKMT_CREATECONTEXTVIRTUAL is used with D3DKMTCreateContextVirtual to create a kernel mode device context that supports virtual addressing.
old-location : display\d3dkmt_createcontextvirtual.htm
old-project : display
ms.assetid : C9707F47-75DF-4CDE-B88B-24323FC8C94B
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DKMT_CREATECONTEXTVIRTUAL structure [Display Devices], display.d3dkmt_createcontextvirtual, D3DKMT_CREATECONTEXTVIRTUAL, _D3DKMT_CREATECONTEXTVIRTUAL, d3dkmthk/D3DKMT_CREATECONTEXTVIRTUAL
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmthk.h
req.include-header : D3dkmthk.h
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
req.typenames : D3DKMT_CREATECONTEXTVIRTUAL
---

# _D3DKMT_CREATECONTEXTVIRTUAL structure
<b>D3DKMT_CREATECONTEXTVIRTUAL</b> is used with <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatecontextvirtual.md">D3DKMTCreateContextVirtual</a> to create a kernel mode device context that supports virtual addressing.

## Syntax
````
typedef struct _D3DKMT_CREATECONTEXTVIRTUAL {
  D3DKMT_HANDLE             hDevice;
  UINT                      NodeOrdinal;
  UINT                      EngineAffinity;
  D3DDDI_CREATECONTEXTFLAGS Flags;
  VOID                      *pPrivateDriverData;
  UINT                      PrivateDriverDataSize;
  D3DKMT_CLIENTHINT         ClientHint;
  D3DKMT_HANDLE             hContext;
} D3DKMT_CREATECONTEXTVIRTUAL;
````

## Members


`ClientHint`

[in] A hint describing which graphics subsystem is creating the context.

`EngineAffinity`

[in] The zero-based index for the engine, within the node that <b>NodeOrdinal</b> specifies, that the context can run in.

`Flags`

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_createcontextflags.md">D3DDDI_CREATECONTEXTFLAGS</a> structure that indicates, in bit-field flags, how to create the context.

`hContext`

[out] A handle to the context that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatecontextvirtual.md">D3DKMTCreateContextVirtual</a> function creates.

`hDevice`

[in] A handle to the device.

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
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatecontextvirtual.md">D3DKMTCreateContextVirtual</a>

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_createcontextflags.md">D3DDDI_CREATECONTEXTFLAGS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CREATECONTEXTVIRTUAL structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>