---
UID: NE:wdfrequest._WDF_REQUEST_REUSE_FLAGS
title: "_WDF_REQUEST_REUSE_FLAGS"
author: windows-driver-content
description: The WDF_REQUEST_REUSE_FLAGS enumeration type defines flags that are used in a driver's WDF_REQUEST_REUSE_PARAMS structure.
old-location: wdf\wdf_request_reuse_flags.htm
old-project: wdf
ms.assetid: 3d1f8f38-b875-4661-9941-4dec28b7e8fb
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_4b91ca45-4dbb-4942-83ce-72ca10170932.xml, WDF_REQUEST_REUSE_FLAGS, WDF_REQUEST_REUSE_FLAGS enumeration, WDF_REQUEST_REUSE_NO_FLAGS, WDF_REQUEST_REUSE_SET_NEW_IRP, _WDF_REQUEST_REUSE_FLAGS, kmdf.wdf_request_reuse_flags, wdf.wdf_request_reuse_flags, wdfrequest/WDF_REQUEST_REUSE_FLAGS, wdfrequest/WDF_REQUEST_REUSE_NO_FLAGS, wdfrequest/WDF_REQUEST_REUSE_SET_NEW_IRP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	wdfrequest.h
api_name:
-	WDF_REQUEST_REUSE_FLAGS
product:
- Windows
targetos: Windows
req.typenames: WDF_REQUEST_REUSE_FLAGS
req.product: Windows 10 or later.
---

# _WDF_REQUEST_REUSE_FLAGS Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_REUSE_FLAGS</b> enumeration type defines flags that are used in a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552480">WDF_REQUEST_REUSE_PARAMS</a> structure.

## Syntax
```
typedef enum _WDF_REQUEST_REUSE_FLAGS {
  WDF_REQUEST_REUSE_NO_FLAGS     ,
  WDF_REQUEST_REUSE_SET_NEW_IRP
} WDF_REQUEST_REUSE_FLAGS;
```

## Constants

<table>
            
                <tr>
                    <td>WDF_REQUEST_REUSE_NO_FLAGS</td>
                    <td>No flags are set.</td>
                </tr>
            
                <tr>
                    <td>WDF_REQUEST_REUSE_SET_NEW_IRP</td>
                    <td>The <b>NewIrp</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552480">WDF_REQUEST_REUSE_PARAMS</a> structure is valid.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfrequest.h (include Wdf.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552480">WDF_REQUEST_REUSE_PARAMS</a>