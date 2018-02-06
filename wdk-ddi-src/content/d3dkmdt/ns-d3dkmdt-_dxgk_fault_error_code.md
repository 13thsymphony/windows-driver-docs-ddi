---
UID: NS:d3dkmdt._DXGK_FAULT_ERROR_CODE
title: "_DXGK_FAULT_ERROR_CODE"
author: windows-driver-content
description: The DXGK_FAULT_ERROR_CODE structure provides a status code for the graphics processing unit (GPU) error reported via a page fault interrupt.
old-location: display\dxgk_fault_error_code.htm
old-project: display
ms.assetid: 753FC177-D430-40E5-98CD-B3BDFD47ACEF
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_FAULT_ERROR_CODE, display.dxgk_fault_error_code, _DXGK_FAULT_ERROR_CODE, d3dkmdt/DXGK_FAULT_ERROR_CODE, DXGK_FAULT_ERROR_CODE structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dkmdt.h
apiname:
-	DXGK_FAULT_ERROR_CODE
product: Windows
targetos: Windows
req.typenames: DXGK_FAULT_ERROR_CODE
---

# _DXGK_FAULT_ERROR_CODE structure
The <b>DXGK_FAULT_ERROR_CODE</b> structure provides a status code for the graphics processing unit (GPU) error reported via a page fault interrupt.

## Syntax
````
typedef struct _DXGK_FAULT_ERROR_CODE {
  union {
    struct {
      UINT                    IsDeviceSpecificCode  :1;
      DXGK_GENERAL_ERROR_CODE GeneralErrorCode  :31;
    };
    struct {
      UINT IsDeviceSpecificCodeReservedBit  :1;
      UINT DeviceSpecificCode  :31;
    };
  };
} DXGK_FAULT_ERROR_CODE;
````

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dkmdt.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmdt\ne-d3dkmdt-_dxgk_general_error_code.md">DXGK_GENERAL_ERROR_CODE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_FAULT_ERROR_CODE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>