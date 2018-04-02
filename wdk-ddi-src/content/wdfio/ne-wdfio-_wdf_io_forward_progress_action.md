---
UID: NE:wdfio._WDF_IO_FORWARD_PROGRESS_ACTION
title: "_WDF_IO_FORWARD_PROGRESS_ACTION"
author: windows-driver-content
description: The WDF_IO_FORWARD_PROGRESS_ACTION enumeration identifies actions that the framework can take for an I/O request packet (IRP) that your driver examines during a low-memory situation.
old-location: wdf\wdf_io_forward_progress_action.htm
old-project: wdf
ms.assetid: 4d63c908-8ae3-4df4-826f-9d87ea6c24ad
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFQueueObjectRef_d1ee566a-9887-44de-aef5-a13f64e7603c.xml, WDF_IO_FORWARD_PROGRESS_ACTION, WDF_IO_FORWARD_PROGRESS_ACTION enumeration, WdfIoForwardProgressActionFailRequest, WdfIoForwardProgressActionInvalid, WdfIoForwardProgressActionUseReservedRequest, _WDF_IO_FORWARD_PROGRESS_ACTION, kmdf.wdf_io_forward_progress_action, wdf.wdf_io_forward_progress_action, wdfio/WDF_IO_FORWARD_PROGRESS_ACTION, wdfio/WdfIoForwardProgressActionFailRequest, wdfio/WdfIoForwardProgressActionInvalid, wdfio/WdfIoForwardProgressActionUseReservedRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfio.h
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfio.h
api_name:
-	WDF_IO_FORWARD_PROGRESS_ACTION
product:
- Windows
targetos: Windows
req.typenames: WDF_IO_FORWARD_PROGRESS_ACTION
req.product: Windows 10 or later.
---

# _WDF_IO_FORWARD_PROGRESS_ACTION Enumeration
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_IO_FORWARD_PROGRESS_ACTION</b> enumeration identifies actions that the framework can take for an I/O request packet (IRP) that your driver examines during a low-memory situation.

## Syntax
```
typedef enum _WDF_IO_FORWARD_PROGRESS_ACTION {
  WdfIoForwardProgressActionInvalid             ,
  WdfIoForwardProgressActionFailRequest         ,
  WdfIoForwardProgressActionUseReservedRequest
} WDF_IO_FORWARD_PROGRESS_ACTION;
```

## Constants

<table>
            
                <tr>
                    <td>WdfIoForwardProgressActionInvalid</td>
                    <td>For internal use only.</td>
                </tr>
            
                <tr>
                    <td>WdfIoForwardProgressActionFailRequest</td>
                    <td>The framework will complete the current I/O request with an error status value.</td>
                </tr>
            
                <tr>
                    <td>WdfIoForwardProgressActionUseReservedRequest</td>
                    <td>The framework will use a reserved request object, if one is available, for the current I/O request.</td>
                </tr>
</table>

## Remarks

The <b>WDF_IO_FORWARD_PROGRESS_ACTION</b> enumeration is used as the return value for the <a href="https://msdn.microsoft.com/71974802-954d-4856-a32b-1dcc45c36ba5">EvtIoWdmIrpForForwardProgress</a> callback function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.9 |
| **Header** | wdfio.h (include Wdf.h) |

## See Also

<a href="https://msdn.microsoft.com/71974802-954d-4856-a32b-1dcc45c36ba5">EvtIoWdmIrpForForwardProgress</a>