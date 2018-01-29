---
UID : NS:d3dkmthk._D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS
title : _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS
author : windows-driver-content
description : The D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS structure identifies attributes of a flip present-history operation.
old-location : display\d3dkmt_flipmodel_presenthistorytokenflags.htm
old-project : display
ms.assetid : 61901e06-fefd-4481-9f19-60ead55bbe36
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3dkmthk/D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS, display.d3dkmt_flipmodel_presenthistorytokenflags, D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS structure [Display Devices], D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS, _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS, OpenGL_Structs_1ffd61bb-ba0b-4ee5-95af-d8c7e38c0b15.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmthk.h
req.include-header : D3dkmthk.h
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 7.
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
req.typenames : D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS
---

# _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS structure
The D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS structure identifies attributes of a flip present-history operation.

## Syntax
````
typedef struct _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS {
  union {
    struct {
      UINT Video  :1;
      UINT RestrictedContent  :1;
      UINT ClipToView  :1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
      UINT StereoPreferRight  :1;
      UINT TemporaryMono  :1;
      UINT FlipRestart  :1;
      UINT ScatterBlt  :1;
      UINT AlphaMode  :2;
      UINT SignalLimitOnTokenCompletion  :1;
      UINT Reserved  :22;
#else 
      UINT Reserved  :29;
#endif 
    };
    UINT   Value;
  };
} D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS;
````

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_presenthistorytoken.md">D3DKMT_PRESENTHISTORYTOKEN</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>