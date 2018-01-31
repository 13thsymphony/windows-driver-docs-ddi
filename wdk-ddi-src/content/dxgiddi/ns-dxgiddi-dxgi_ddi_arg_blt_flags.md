---
UID : NS:dxgiddi.DXGI_DDI_ARG_BLT_FLAGS
title : DXGI_DDI_ARG_BLT_FLAGS
author : windows-driver-content
description : The DXGI_DDI_ARG_BLT_FLAGS structure identifies the type of bit-block transfer (bitblt) to perform.
old-location : display\dxgi_ddi_arg_blt_flags.htm
old-project : display
ms.assetid : 812679d2-b05c-4533-b4b2-01b973b0d80f
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.dxgi_ddi_arg_blt_flags, DXGI_DDI_ARG_BLT_FLAGS structure [Display Devices], dxgiddi/DXGI_DDI_ARG_BLT_FLAGS, DXGI_DDI_ARG_BLT_FLAGS, UMDisplayDriver_Dx10param_Structs_22ccf0e7-83cc-443e-b4a1-c1a2f3bc24a0.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : dxgiddi.h
req.include-header : D3d10umddi.h
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
req.typenames : DXGI_DDI_ARG_BLT_FLAGS
---

# DXGI_DDI_ARG_BLT_FLAGS structure
The DXGI_DDI_ARG_BLT_FLAGS structure identifies the type of bit-block transfer (bitblt) to perform.

## Syntax
````
typedef struct DXGI_DDI_ARG_BLT_FLAGS {
  union {
    struct {
      UINT Resolve  :1;
      UINT Convert  :1;
      UINT Stretch  :1;
      UINT Present  :1;
      UINT Reserved  :28;
    };
    UINT   Value;
  };
} DXGI_DDI_ARG_BLT_FLAGS;
````

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dxgiddi.h (include D3d10umddi.h) |

## See Also

<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_arg_blt.md">DXGI_DDI_ARG_BLT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_ARG_BLT_FLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>