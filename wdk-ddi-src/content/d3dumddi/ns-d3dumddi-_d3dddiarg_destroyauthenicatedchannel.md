---
UID: NS:d3dumddi._D3DDDIARG_DESTROYAUTHENICATEDCHANNEL
title: "_D3DDDIARG_DESTROYAUTHENICATEDCHANNEL"
author: windows-driver-content
description: The D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL structure contains the handle to an authenticated channel that is destroyed in a call to the DestroyAuthenticatedChannel function.
old-location: display\d3dddiarg_destroyauthenticatedchannel.htm
old-project: display
ms.assetid: 3b953c73-a033-465a-a041-7c21ee307c32
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL, D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL structure [Display Devices], UMDisplayDriver_param_Structs_be6187b3-2d01-450e-90a7-d01a97aba764.xml, _D3DDDIARG_DESTROYAUTHENICATEDCHANNEL, d3dumddi/D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL, display.d3dddiarg_destroyauthenticatedchannel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL is supported beginning with the Windows 7 operating system.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL
---

# _D3DDDIARG_DESTROYAUTHENICATEDCHANNEL structure
The D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL structure contains the handle to an authenticated channel that is destroyed in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451630">DestroyAuthenticatedChannel</a> function.

## Syntax
```
typedef struct _D3DDDIARG_DESTROYAUTHENICATEDCHANNEL {
  HANDLE hChannel;
} D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL;
```

## Members


`hChannel`

[in] The handle to the authenticated channel that the driver destroys.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL is supported beginning with the Windows 7 operating system. D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL is supported beginning with the Windows 7 operating system. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451630">DestroyAuthenticatedChannel</a>