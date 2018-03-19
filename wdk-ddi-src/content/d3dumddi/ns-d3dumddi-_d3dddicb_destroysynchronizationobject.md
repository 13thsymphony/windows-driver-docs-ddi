---
UID: NS:d3dumddi._D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT
title: "_D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT"
author: windows-driver-content
description: The D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure contains the handle to a synchronization object to destroy.
old-location: display\d3dddicb_destroysynchronizationobject.htm
old-project: display
ms.assetid: d950e290-3acb-4a89-86a4-ae5117781998
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT, D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure [Display Devices], D3D_param_Structs_34603e42-8f8b-42cb-9191-988be4a8932d.xml, _D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT, d3dumddi/D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT, display.d3dddicb_destroysynchronizationobject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT
product: Windows
targetos: Windows
req.typenames: D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT
---

# _D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure
The D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure contains the handle to a synchronization object to destroy.

## Syntax
````
typedef struct _D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT {
  D3DKMT_HANDLE hSyncObject;
} D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT;
````

## Members


`hSyncObject`

[in] A D3DKMT_HANDLE value that represents the kernel-mode handle that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb.md">pfnCreateSynchronizationObjectCb</a> function returns and that identifies the kernel-mode synchronization object to destroy.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb.md">pfnDestroySynchronizationObjectCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb.md">pfnCreateSynchronizationObjectCb</a>