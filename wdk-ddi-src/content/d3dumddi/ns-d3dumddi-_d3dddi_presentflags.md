---
UID : NS:d3dumddi._D3DDDI_PRESENTFLAGS
title : _D3DDDI_PRESENTFLAGS
author : windows-driver-content
description : The D3DDDI_PRESENTFLAGS structure identifies how to perform a present operation.
old-location : display\d3dddi_presentflags.htm
old-project : display
ms.assetid : adab4c0f-b879-409c-97a3-f161a50514f5
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D_other_Structs_4650db5e-637b-4032-a5d2-ded887a883dc.xml, display.d3dddi_presentflags, _D3DDDI_PRESENTFLAGS, D3DDDI_PRESENTFLAGS structure [Display Devices], D3DDDI_PRESENTFLAGS, d3dumddi/D3DDDI_PRESENTFLAGS
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
req.typenames : D3DDDI_PRESENTFLAGS
---

# _D3DDDI_PRESENTFLAGS structure
The D3DDDI_PRESENTFLAGS structure identifies how to perform a present operation.

## Syntax
````
typedef struct _D3DDDI_PRESENTFLAGS {
  union {
    struct {
      UINT Blt  :1;
      UINT ColorFill  :1;
      UINT Flip  :1;
      UINT Reserved  :29;
    };
    UINT   Value;
  };
} D3DDDI_PRESENTFLAGS;
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

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_present.md">Present</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_present.md">D3DDDIARG_PRESENT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_PRESENTFLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>