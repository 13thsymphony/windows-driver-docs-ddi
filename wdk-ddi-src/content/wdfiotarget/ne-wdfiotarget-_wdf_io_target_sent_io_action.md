---
UID: NE:wdfiotarget._WDF_IO_TARGET_SENT_IO_ACTION
title: "_WDF_IO_TARGET_SENT_IO_ACTION"
author: windows-driver-content
description: The WDF_IO_TARGET_SENT_IO_ACTION enumeration identifies the actions that the framework can take when a driver calls WdfIoTargetStop to stop an I/O target.
old-location: wdf\wdf_io_target_sent_io_action.htm
old-project: wdf
ms.assetid: 4295ef73-b9a8-4593-8114-d0b836275b13
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFIOTargetRef_f9150c63-6b0b-4050-b4ae-fd5ebbda4e0d.xml, WDF_IO_TARGET_SENT_IO_ACTION, WDF_IO_TARGET_SENT_IO_ACTION enumeration, WdfIoTargetCancelSentIo, WdfIoTargetLeaveSentIoPending, WdfIoTargetSentIoUndefined, WdfIoTargetWaitForSentIoToComplete, _WDF_IO_TARGET_SENT_IO_ACTION, kmdf.wdf_io_target_sent_io_action, wdf.wdf_io_target_sent_io_action, wdfiotarget/WDF_IO_TARGET_SENT_IO_ACTION, wdfiotarget/WdfIoTargetCancelSentIo, wdfiotarget/WdfIoTargetLeaveSentIoPending, wdfiotarget/WdfIoTargetSentIoUndefined, wdfiotarget/WdfIoTargetWaitForSentIoToComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfiotarget.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfiotarget.h
api_name:
-	WDF_IO_TARGET_SENT_IO_ACTION
product: Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_SENT_IO_ACTION
req.product: Windows 10 or later.
---

# _WDF_IO_TARGET_SENT_IO_ACTION Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_TARGET_SENT_IO_ACTION</b> enumeration identifies the actions that the framework can take when a driver calls <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstop.md">WdfIoTargetStop</a> to stop an I/O target.

## Syntax
````
typedef enum _WDF_IO_TARGET_SENT_IO_ACTION { 
  WdfIoTargetSentIoUndefined          = 0,
  WdfIoTargetCancelSentIo             = 1,
  WdfIoTargetWaitForSentIoToComplete  = 2,
  WdfIoTargetLeaveSentIoPending       = 3
} WDF_IO_TARGET_SENT_IO_ACTION;
````

## Constants

<table>
            
                <tr>
                    <td>WdfIoTargetSentIoUndefined</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>WdfIoTargetCancelSentIo</td>
                    <td>Before the framework stops the I/O target, it will attempt to cancel I/O requests that are in the I/O target's queue. The framework cancels all of the target queue's I/O requests, and waits for all I/O requests to complete, before <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstop.md">WdfIoTargetStop</a> returns. The framework also attempts to cancel I/O requests that have left the I/O target's queue and entered lower drivers.</td>
                </tr>
            
                <tr>
                    <td>WdfIoTargetWaitForSentIoToComplete</td>
                    <td>Before the framework stops the I/O target, it will wait for I/O requests that are in the I/O target's queue to be completed. The framework completes all of the target queue's I/O requests, and calls each request's <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function, before <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstop.md">WdfIoTargetStop</a> returns.</td>
                </tr>
            
                <tr>
                    <td>WdfIoTargetLeaveSentIoPending</td>
                    <td>The framework will leave I/O requests in the I/O target's queue. The requests remain in the target's queue until the driver calls <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstart.md">WdfIoTargetStart</a> or the device is removed.</td>
                </tr>
</table>

## Remarks

The <b>WDF_IO_TARGET_SENT_IO_ACTION</b> enumeration is used as an input parameter to the <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstop.md">WdfIoTargetStop</a> method.

If your driver specifies the <b>WdfIoTargetWaitForSentIoToComplete</b> flag, the driver must not call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstop.md">WdfIoTargetStop</a> from a request handler, a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function, or an <a href="..\wdfusb\nc-wdfusb-evt_wdf_usb_readers_failed.md">EvtUsbTargetPipeReadersFailed</a> callback function.

For the UMDF version of this enumeration, see <a href="..\wdfiotarget\ne-wdfiotarget-_wdf_io_target_sent_io_action.md">WDF_IO_TARGET_SENT_IO_ACTION (UMDF)</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfiotarget.h (include Wdf.h) |

## See Also

<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstop.md">WdfIoTargetStop</a>