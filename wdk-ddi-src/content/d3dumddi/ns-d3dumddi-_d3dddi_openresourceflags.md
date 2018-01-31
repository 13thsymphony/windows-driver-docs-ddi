---
UID : NS:d3dumddi._D3DDDI_OPENRESOURCEFLAGS
title : "_D3DDDI_OPENRESOURCEFLAGS"
author : windows-driver-content
description : The D3DDDI_OPENRESOURCEFLAGS structure identifies the type of resource to open.
old-location : display\d3dddi_openresourceflags.htm
old-project : display
ms.assetid : f65fda13-3d05-4e1b-b0c7-01e43a9bf09e
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3dumddi/D3DDDI_OPENRESOURCEFLAGS, display.d3dddi_openresourceflags, D3D_other_Structs_918a41c9-09de-4916-a0d6-fd69f7c431c2.xml, D3DDDI_OPENRESOURCEFLAGS, D3DDDI_OPENRESOURCEFLAGS structure [Display Devices], _D3DDDI_OPENRESOURCEFLAGS
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
req.typenames : D3DDDI_OPENRESOURCEFLAGS
---

# _D3DDDI_OPENRESOURCEFLAGS structure
The D3DDDI_OPENRESOURCEFLAGS structure identifies the type of resource to open.

## Syntax
````
typedef struct _D3DDDI_OPENRESOURCEFLAGS {
  union {
    struct {
      UINT Fullscreen  :1;
      UINT AlphaOverride  :1;
      UINT Reserved  :30;
    };
    UINT   Value;
  };
} D3DDDI_OPENRESOURCEFLAGS;
````

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_openresource.md">D3DDDIARG_OPENRESOURCE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_OPENRESOURCEFLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>