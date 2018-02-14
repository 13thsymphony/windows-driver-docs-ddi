---
UID: NC:d3dumddi.PFND3DDDI_UPDATESUBRESOURCEUP
title: PFND3DDDI_UPDATESUBRESOURCEUP
author: windows-driver-content
description: Called by the Microsoft Direct3D runtime to update a destination subresource region from a source system-memory region. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\pfnupdatesubresourceup.htm
old-project: display
ms.assetid: 5AF55FED-6FD6-41BE-A743-1E9D0EA51C9C
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnupdatesubresourceup, pfnUpdateSubresourceUP callback function [Display Devices], pfnUpdateSubresourceUP, PFND3DDDI_UPDATESUBRESOURCEUP, PFND3DDDI_UPDATESUBRESOURCEUP, d3dumddi/pfnUpdateSubresourceUP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3dumddi.h
apiname:
-	pfnUpdateSubresourceUP
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_UPDATESUBRESOURCEUP callback function
Called by the Microsoft Direct3D runtime to update a destination subresource region from a source system-memory region. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.

## Syntax

```
PFND3DDDI_UPDATESUBRESOURCEUP Pfnd3dddiUpdatesubresourceup;

HRESULT Pfnd3dddiUpdatesubresourceup(
  HANDLE hDevice,
  CONST D3DDDIARG_UPDATESUBRESOURCEUP *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

If this routine succeeds, it returns <b>S_OK</b>. Otherwise, it returns an <b>HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-d3dddiarg_updatesubresourceup.md">D3DDDIARG_UPDATESUBRESOURCEUP</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_UPDATESUBRESOURCEUP callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>