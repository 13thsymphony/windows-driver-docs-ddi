---
UID: NS:d3d10umddi.D3D11DDIARG_CREATECOMMANDLIST
title: D3D11DDIARG_CREATECOMMANDLIST
author: windows-driver-content
description: The D3D11DDIARG_CREATECOMMANDLIST structure contains a handle to the deferred context that was created by the CreateDeferredContext function.
old-location: display\d3d11ddiarg_createcommandlist.htm
old-project: display
ms.assetid: 7d720346-4a68-40bd-816d-c406995b3232
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/D3D11DDIARG_CREATECOMMANDLIST, UMDisplayDriver_Dx11param_Structs_fc1a42ad-2d14-44de-abf1-480810b8d080.xml, display.d3d11ddiarg_createcommandlist, D3D11DDIARG_CREATECOMMANDLIST, D3D11DDIARG_CREATECOMMANDLIST structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_CREATECOMMANDLIST is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
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
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D11DDIARG_CREATECOMMANDLIST
product: Windows
targetos: Windows
req.typenames: D3D11DDIARG_CREATECOMMANDLIST
---

# D3D11DDIARG_CREATECOMMANDLIST structure
The D3D11DDIARG_CREATECOMMANDLIST structure contains a handle to the deferred context that was created by the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createdeferredcontext.md">CreateDeferredContext</a> function.

## Syntax
````
typedef struct D3D11DDIARG_CREATECOMMANDLIST {
  D3D10DDI_HDEVICE hDeferredContext;
} D3D11DDIARG_CREATECOMMANDLIST;
````

## Members


`hDeferredContext`

[in] A handle to the deferred context.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3D11DDIARG_CREATECOMMANDLIST is supported beginning with the Windows 7 operating system. D3D11DDIARG_CREATECOMMANDLIST is supported beginning with the Windows 7 operating system. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createdeferredcontext.md">CreateDeferredContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11DDIARG_CREATECOMMANDLIST structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>