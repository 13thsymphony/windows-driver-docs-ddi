---
UID: NS:d3dkmddi._DXGK_CREATECONTEXTALLOCATIONFLAGS
title: "_DXGK_CREATECONTEXTALLOCATIONFLAGS"
author: windows-driver-content
description: Specifies the properties of the context to be allocated.
old-location: display\dxgk_createcontextallocationflags.htm
old-project: display
ms.assetid: e80a314d-cef1-4289-84db-0a6b6531ae5f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGK_CREATECONTEXTALLOCATIONFLAGS, DXGK_CREATECONTEXTALLOCATIONFLAGS, display.dxgk_createcontextallocationflags, DXGK_CREATECONTEXTALLOCATIONFLAGS structure [Display Devices], _DXGK_CREATECONTEXTALLOCATIONFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dkmddi.h
apiname:
-	DXGK_CREATECONTEXTALLOCATIONFLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_CREATECONTEXTALLOCATIONFLAGS
---

# _DXGK_CREATECONTEXTALLOCATIONFLAGS structure
Specifies the properties of the context to be allocated.

## Syntax
````
typedef struct _DXGK_CREATECONTEXTALLOCATIONFLAGS {
  union {
    struct {
      UINT SharedAcrossContexts  :1;
      UINT Reserved  :31;
    };
    UINT Value;
  };
} DXGK_CREATECONTEXTALLOCATIONFLAGS;
````

## Members


## Remarks
The display miniport driver allocates GPU contexts or device-specific contexts by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_createcontextallocation.md">DxgkCbCreateContextAllocation</a>.

The <b>ContextAllocationFlags</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_createcontextallocation.md">DXGKARGCB_CREATECONTEXTALLOCATION</a> structure is an <b>DXGK_CREATECONTEXTALLOCATIONFLAGS</b> data type.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_createcontextallocation.md">DXGKARGCB_CREATECONTEXTALLOCATION</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_createcontextallocation.md">DxgkCbCreateContextAllocation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20 DXGK_CREATECONTEXTALLOCATIONFLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>