---
UID: NS:d3dukmdt.D3DDDI_TRIMRESIDENCYSET_FLAGS
title: D3DDDI_TRIMRESIDENCYSET_FLAGS
author: windows-driver-content
description: D3DDDI_TRIMRESIDENCYSET_FLAGS is used with pfnTrimResidencySet to trim the residency list for a given device.
old-location: display\d3dddi_trimresidencyset_flags.htm
old-project: display
ms.assetid: B063561B-FA79-44B4-A058-71DB9CBF4804
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DDDI_TRIMRESIDENCYSET_FLAGS, D3DDDI_TRIMRESIDENCYSET_FLAGS structure [Display Devices], d3dukmdt/D3DDDI_TRIMRESIDENCYSET_FLAGS, display.d3dddi_trimresidencyset_flags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dukmdt.h
api_name:
-	D3DDDI_TRIMRESIDENCYSET_FLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDI_TRIMRESIDENCYSET_FLAGS
---

# D3DDDI_TRIMRESIDENCYSET_FLAGS structure
<b>D3DDDI_TRIMRESIDENCYSET_FLAGS</b> is used with <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_trimresidencyset.md">pfnTrimResidencySet</a> to trim the residency list for a given device.

## Syntax
````
typedef struct D3DDDI_TRIMRESIDENCYSET_FLAGS {
  union {
    struct {
      UINT PeriodicTrim  :1;
      UINT RestartPeriodicTrim  :1;
      UINT TrimToBudget  :1;
      UINT Reserved  :29;
    };
    UINT Value;
  };
} D3DDDI_TRIMRESIDENCYSET_FLAGS;
````

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dukmdt.h (include D3dumddi.h, D3dkmddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_trimresidencyset.md">pfnTrimResidencySet</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_TRIMRESIDENCYSET_FLAGS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>