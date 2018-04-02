---
UID: NE:wdfio._WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY
title: "_WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY"
author: windows-driver-content
description: The WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY enumeration identifies actions that the framework can take when it receives an I/O request for your driver, if a low-memory situation exists.
old-location: wdf\wdf_io_forward_progress_reserved_policy.htm
old-project: wdf
ms.assetid: 6d530cf2-de06-4aa3-9f4d-08619906c9ed
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFQueueObjectRef_e035ecd7-f728-4d88-80a8-763ab3eb90ab.xml, WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY, WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY enumeration, WdfIoForwardProgressInvalidPolicy, WdfIoForwardProgressReservedPolicyAlwaysUseReservedRequest, WdfIoForwardProgressReservedPolicyPagingIO, WdfIoForwardProgressReservedPolicyUseExamine, _WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY, kmdf.wdf_io_forward_progress_reserved_policy, wdf.wdf_io_forward_progress_reserved_policy, wdfio/WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY, wdfio/WdfIoForwardProgressInvalidPolicy, wdfio/WdfIoForwardProgressReservedPolicyAlwaysUseReservedRequest, wdfio/WdfIoForwardProgressReservedPolicyPagingIO, wdfio/WdfIoForwardProgressReservedPolicyUseExamine
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
-	WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY
product:
- Windows
targetos: Windows
req.typenames: WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY
req.product: Windows 10 or later.
---

# _WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY Enumeration
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY</b> enumeration identifies actions that the framework can take when it receives an I/O request for your driver, if a low-memory situation exists.

## Syntax
```
typedef enum _WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY {
  WdfIoForwardProgressInvalidPolicy                           ,
  WdfIoForwardProgressReservedPolicyAlwaysUseReservedRequest  ,
  WdfIoForwardProgressReservedPolicyUseExamine                ,
  WdfIoForwardProgressReservedPolicyPagingIO
} WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY;
```

## Constants

<table>
            
                <tr>
                    <td>WdfIoForwardProgressInvalidPolicy</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WdfIoForwardProgressReservedPolicyAlwaysUseReservedRequest</td>
                    <td>In a low-memory situation, the framework always uses a reserved request object, if one is available.</td>
                </tr>
            
                <tr>
                    <td>WdfIoForwardProgressReservedPolicyUseExamine</td>
                    <td>In a low-memory situation, the framework calls the driver's <a href="https://msdn.microsoft.com/71974802-954d-4856-a32b-1dcc45c36ba5">EvtIoWdmIrpForForwardProgress</a> callback function.</td>
                </tr>
            
                <tr>
                    <td>WdfIoForwardProgressReservedPolicyPagingIO</td>
                    <td>In a low-memory situation, if the <b>Flags</b> member of the I/O request's <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure indicates a paging operation, the framework uses a reserved request object, if one is available. If the I/O request is not a paging operation, the framework completes the I/O request with an error status value.</td>
                </tr>
</table>

## Remarks

The <b>WDF_IO_FORWARD_PROGRESS_RESERVED_POLICY</b> enumeration is used as a member type in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552364">WDF_IO_QUEUE_FORWARD_PROGRESS_POLICY</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.9 |
| **Header** | wdfio.h (include Wdf.h) |