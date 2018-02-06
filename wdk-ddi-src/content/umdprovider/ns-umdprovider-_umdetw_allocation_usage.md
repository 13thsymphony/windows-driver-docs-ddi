---
UID: NS:umdprovider._UMDETW_ALLOCATION_USAGE
title: "_UMDETW_ALLOCATION_USAGE"
author: windows-driver-content
description: Indicates the reason for mapping from a Microsoft Direct3D memory allocation to a Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys) allocation.
old-location: display\umdetw_allocation_usage.htm
old-project: display
ms.assetid: 40522471-0fbc-4193-8164-60138e3862fe
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: UMDETW_ALLOCATION_USAGE, umdprovider/UMDETW_ALLOCATION_USAGE, _UMDETW_ALLOCATION_USAGE, display.umdetw_allocation_usage, UMDETW_ALLOCATION_USAGE structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: umdprovider.h
req.include-header: Umdprovider.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	umdprovider.h
apiname:
-	UMDETW_ALLOCATION_USAGE
product: Windows
targetos: Windows
req.typenames: UMDETW_ALLOCATION_USAGE
req.product: Windows 10 or later.
---

# _UMDETW_ALLOCATION_USAGE structure
Indicates the reason for mapping from a Microsoft Direct3D  memory allocation to a Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys) allocation.

## Syntax
````
typedef struct _UMDETW_ALLOCATION_USAGE {
  union {
    struct {
      UINT Packed  :1;
      UINT Renamed  :1;
      UINT Reserved  :14;
      UINT DriverReserved  :16;
    };
    UINT   Value;
  };
} UMDETW_ALLOCATION_USAGE;
````

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | umdprovider.h (include Umdprovider.h) |

## See Also

<a href="..\umdprovider\nf-umdprovider-umdetwlogmapallocation.md">UMDEtwLogMapAllocation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20UMDETW_ALLOCATION_USAGE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>