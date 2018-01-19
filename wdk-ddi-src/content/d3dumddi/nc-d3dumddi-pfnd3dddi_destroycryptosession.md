---
UID : NC:d3dumddi.PFND3DDDI_DESTROYCRYPTOSESSION
title : PFND3DDDI_DESTROYCRYPTOSESSION
author : windows-driver-content
description : The DestroyCryptoSession function releases resources for the encryption session that the CreateCryptoSession function creates.
old-location : display\destroycryptosession.htm
old-project : display
ms.assetid : 4035ef73-e1a2-49e4-808d-c40c980393a4
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXGK_PTE, DXGK_PTE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Desktop
req.target-min-winverclnt : DestroyCryptoSession is supported beginning with the Windows 7 operating system.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DestroyCryptoSession
req.alt-loc : d3dumddi.h
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
req.typenames : DXGK_PTE
---


# PFND3DDDI_DESTROYCRYPTOSESSION callback function
The <b>DestroyCryptoSession</b> function releases resources for the encryption session that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a> function creates.

## Syntax

```
PFND3DDDI_DESTROYCRYPTOSESSION Pfnd3dddiDestroycryptosession;

HRESULT Pfnd3dddiDestroycryptosession(
  HANDLE hDevice,
  CONST D3DDDIARG_DESTROYCRYPTOSESSION *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<b>DestroyCryptoSession</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The encryption session is successfully destroyed. 
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroycryptosession.md">DestroyCryptoSession</a> could not allocate the required memory for it to complete.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_destroycryptosession.md">D3DDDIARG_DESTROYCRYPTOSESSION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DESTROYCRYPTOSESSION callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>