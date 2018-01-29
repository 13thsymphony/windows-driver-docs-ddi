---
UID : NS:d3dumddi._D3DDDIARG_DESTROYOVERLAY
title : _D3DDDIARG_DESTROYOVERLAY
author : windows-driver-content
description : The D3DDDIARG_DESTROYOVERLAY structure contains a handle to the overlay to disable.
old-location : display\d3dddiarg_destroyoverlay.htm
old-project : display
ms.assetid : a468205c-288c-49d5-ab14-0ee39dca7b7c
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3dumddi/D3DDDIARG_DESTROYOVERLAY, D3DDDIARG_DESTROYOVERLAY, UMDisplayDriver_param_Structs_e7a2d82a-2e1c-4362-ae4d-23617911de3b.xml, display.d3dddiarg_destroyoverlay, _D3DDDIARG_DESTROYOVERLAY, D3DDDIARG_DESTROYOVERLAY structure [Display Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
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
req.typenames : D3DDDIARG_DESTROYOVERLAY
---

# _D3DDDIARG_DESTROYOVERLAY structure
The D3DDDIARG_DESTROYOVERLAY structure contains a handle to the overlay to disable.

## Syntax
````
typedef struct _D3DDDIARG_DESTROYOVERLAY {
  HANDLE hOverlay;
} D3DDDIARG_DESTROYOVERLAY;
````

## Members


`hOverlay`

[in] A handle to the overlay to disable.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyoverlay.md">DestroyOverlay</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DESTROYOVERLAY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>