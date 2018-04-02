---
UID: NE:wdfrequest._WDF_REQUEST_FORWARD_OPTIONS_FLAGS
title: "_WDF_REQUEST_FORWARD_OPTIONS_FLAGS"
author: windows-driver-content
description: The WDF_REQUEST_FORWARD_OPTIONS_FLAGS enumeration type defines flags that are used in a driver's WDF_REQUEST_FORWARD_OPTIONS structure.
old-location: wdf\wdf_request_forward_options_flags.htm
old-project: wdf
ms.assetid: 6161bfd3-482c-4571-bd88-2e25d32b34a0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_cad8f6c6-9c76-4dc3-ac3f-3938e5174563.xml, WDF_REQUEST_FORWARD_OPTIONS_FLAGS, WDF_REQUEST_FORWARD_OPTIONS_FLAGS enumeration, WDF_REQUEST_FORWARD_OPTION_SEND_AND_FORGET, _WDF_REQUEST_FORWARD_OPTIONS_FLAGS, kmdf.wdf_request_forward_options_flags, wdf.wdf_request_forward_options_flags, wdfrequest/WDF_REQUEST_FORWARD_OPTIONS_FLAGS, wdfrequest/WDF_REQUEST_FORWARD_OPTION_SEND_AND_FORGET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
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
-	wdfrequest.h
api_name:
-	WDF_REQUEST_FORWARD_OPTIONS_FLAGS
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_FORWARD_OPTIONS_FLAGS
req.product: Windows 10 or later.
---

# _WDF_REQUEST_FORWARD_OPTIONS_FLAGS Enumeration
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_REQUEST_FORWARD_OPTIONS_FLAGS</b> enumeration type defines flags that are used in a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552459">WDF_REQUEST_FORWARD_OPTIONS</a> structure.

## Syntax
```
typedef enum _WDF_REQUEST_FORWARD_OPTIONS_FLAGS {
  WDF_REQUEST_FORWARD_OPTION_SEND_AND_FORGET
} WDF_REQUEST_FORWARD_OPTIONS_FLAGS;
```

## Constants

<table>
            
                <tr>
                    <td>WDF_REQUEST_FORWARD_OPTION_SEND_AND_FORGET</td>
                    <td>If set, the driver does not need to be notified when the request is completed or canceled. The driver does not set a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function or call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> for the request.</td>
                </tr>
</table>

## Remarks

Currently, drivers must set the WDF_REQUEST_FORWARD_OPTION_SEND_AND_FORGET flag.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.9 |
| **Header** | wdfrequest.h (include Wdf.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552459">WDF_REQUEST_FORWARD_OPTIONS</a>