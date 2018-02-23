---
UID: NS:d3dumddi._D3DDDIARG_DESTROYLIGHT
title: "_D3DDDIARG_DESTROYLIGHT"
author: windows-driver-content
description: The D3DDDIARG_DESTROYLIGHT structure contains the index into a light array for the light to destroy.
old-location: display\d3dddiarg_destroylight.htm
old-project: display
ms.assetid: d019a940-5735-4b35-af99-3aac3dc4270b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "_D3DDDIARG_DESTROYLIGHT, display.d3dddiarg_destroylight, D3DDDIARG_DESTROYLIGHT, D3DDDIARG_DESTROYLIGHT structure [Display Devices], UMDisplayDriver_param_Structs_497b7bc8-b2ca-4ead-9c3e-365673b2058f.xml, d3dumddi/D3DDDIARG_DESTROYLIGHT"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_DESTROYLIGHT
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_DESTROYLIGHT
---

# _D3DDDIARG_DESTROYLIGHT structure
The D3DDDIARG_DESTROYLIGHT structure contains the index into a light array for the light to destroy.

## Syntax
````
typedef struct _D3DDDIARG_DESTROYLIGHT {
  UINT Index;
} D3DDDIARG_DESTROYLIGHT;
````

## Members


`Index`

[in] The index of the light to destroy.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroylight.md">DestroyLight</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DESTROYLIGHT structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>