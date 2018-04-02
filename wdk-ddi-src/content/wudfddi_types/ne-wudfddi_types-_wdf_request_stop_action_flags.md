---
UID: NE:wudfddi_types._WDF_REQUEST_STOP_ACTION_FLAGS
title: "_WDF_REQUEST_STOP_ACTION_FLAGS"
author: windows-driver-content
description: The WDF_REQUEST_STOP_ACTION_FLAGS enumeration contains values that identify the state of a stop action request in a call to the driver's IQueueCallbackIoStop::OnIoStop method.
old-location: wdf\wdf_request_stop_action_flags_umdf.htm
old-project: wdf
ms.assetid: b9e3ea22-be24-4f36-abde-339495b9ed1c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_REQUEST_STOP_ACTION_FLAGS, WDF_REQUEST_STOP_ACTION_FLAGS enumeration, WdfRequestStopActionInvalid, WdfRequestStopActionPurge, WdfRequestStopActionSuspend, WdfRequestStopRequestCancelable, _WDF_REQUEST_STOP_ACTION_FLAGS, umdf.wdf_request_stop_action_flags, umdfstructs_ecbf4eac-7d5f-4c44-a8c3-96731737264b.xml, wdf.wdf_request_stop_action_flags_umdf, wudfddi_types/WDF_REQUEST_STOP_ACTION_FLAGS, wudfddi_types/WdfRequestStopActionInvalid, wudfddi_types/WdfRequestStopActionPurge, wudfddi_types/WdfRequestStopActionSuspend, wudfddi_types/WdfRequestStopRequestCancelable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
-	Wudfddi_types.h
api_name:
-	WDF_REQUEST_STOP_ACTION_FLAGS
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_STOP_ACTION_FLAGS
req.product: Windows 10 or later.
---

# _WDF_REQUEST_STOP_ACTION_FLAGS Enumeration
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561465">WDF_REQUEST_STOP_ACTION_FLAGS</a> enumeration contains values that identify the state of a stop action request in a call to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556871">IQueueCallbackIoStop::OnIoStop</a> method.

## Syntax
```
typedef enum _WDF_REQUEST_STOP_ACTION_FLAGS {
  WdfRequestStopActionInvalid      ,
  WdfRequestStopActionSuspend      ,
  WdfRequestStopActionPurge        ,
  WdfRequestStopRequestCancelable
} WDF_REQUEST_STOP_ACTION_FLAGS;
```

## Constants

<table>
            
                <tr>
                    <td>WdfRequestStopActionInvalid</td>
                    <td>If this value is set to 1, the request is invalid.</td>
                </tr>
            
                <tr>
                    <td>WdfRequestStopActionSuspend</td>
                    <td>If this value is set to 1, the device is suspended.</td>
                </tr>
            
                <tr>
                    <td>WdfRequestStopActionPurge</td>
                    <td>If this value is set to 1, the device and queue are removed.</td>
                </tr>
            
                <tr>
                    <td>WdfRequestStopRequestCancelable</td>
                    <td>If this value is set to 1, the request is marked as cancelable.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wudfddi_types.h (include Wudfddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556871">IQueueCallbackIoStop::OnIoStop</a>