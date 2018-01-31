---
UID : NE:wudfddi_types._WDF_IO_TARGET_SENT_IO_ACTION
title : "_WDF_IO_TARGET_SENT_IO_ACTION"
author : windows-driver-content
description : The WDF_IO_TARGET_SENT_IO_ACTION enumeration identifies the actions that the framework can take when a driver calls IWDFIoTargetStateManagement::Stop or IWDFRemoteTarget::Stop to stop an I/O target.
old-location : wdf\wdf_io_target_sent_io_action__umdf_.htm
old-project : wdf
ms.assetid : 9cdcf964-9f2d-437f-8693-de5bb4bb9895
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.wdf_io_target_sent_io_action__umdf_, WdfIoTargetCancelSentIo, wudfddi_types/WdfIoTargetWaitForSentIoToComplete, umdf.wdf_io_target_sent_io_action__umdf_, wudfddi_types/WdfIoTargetSentIoUndefined, _WDF_IO_TARGET_SENT_IO_ACTION, WdfIoTargetWaitForSentIoToComplete, WDF_IO_TARGET_SENT_IO_ACTION enumeration, wudfddi_types/WdfIoTargetSentIoMaximum, WdfIoTargetLeaveSentIoPending, umdfstructs_c5c41acc-35ac-4894-bb1b-af3b3a9b75d1.xml, wudfddi_types/WdfIoTargetCancelSentIo, wudfddi_types/WdfIoTargetLeaveSentIoPending, wudfddi_types/WDF_IO_TARGET_SENT_IO_ACTION, WDF_IO_TARGET_SENT_IO_ACTION, WdfIoTargetSentIoMaximum, WdfIoTargetSentIoUndefined
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wudfddi_types.h
req.include-header : Wudfddi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.0
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_IO_TARGET_SENT_IO_ACTION
req.product : Windows 10 or later.
---

# _WDF_IO_TARGET_SENT_IO_ACTION Enumeration
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


      The <b>WDF_IO_TARGET_SENT_IO_ACTION</b> enumeration identifies the actions that the framework can take when a driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff559217">IWDFIoTargetStateManagement::Stop</a> or  <a href="https://msdn.microsoft.com/library/windows/hardware/ff560289">IWDFRemoteTarget::Stop</a> to stop an I/O target.

## Syntax
````
typedef enum _WDF_IO_TARGET_SENT_IO_ACTION { 
  WdfIoTargetSentIoUndefined          = 0,
  WdfIoTargetCancelSentIo             = 1,
  WdfIoTargetWaitForSentIoToComplete  = 2,
  WdfIoTargetLeaveSentIoPending       = 3,
  WdfIoTargetSentIoMaximum            = ( WdfIoTargetLeaveSentIoPending + 1 )
} WDF_IO_TARGET_SENT_IO_ACTION;
````

## Constants

<table>

<tr>
<td>WdfIoTargetCancelSentIo</td>
<td>Before the framework stops the I/O target, it will attempt to cancel I/O requests that are in the I/O target's queue. The framework cancels all of the target queue's I/O requests before <a href="https://msdn.microsoft.com/library/windows/hardware/ff559217">IWDFIoTargetStateManagement::Stop</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff560289">IWDFRemoteTarget::Stop</a> returns.</td>
</tr>

<tr>
<td>WdfIoTargetLeaveSentIoPending</td>
<td>The framework will leave I/O requests in the I/O target's queue. The requests remain in the target's queue until the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff559213">IWDFIoTargetStateManagement::Start</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff560280">IWDFRemoteTarget::Start</a> or the device is removed.</td>
</tr>

<tr>
<td>WdfIoTargetSentIoMaximum</td>
<td>Valid enumeration values were exceeded.</td>
</tr>

<tr>
<td>WdfIoTargetSentIoUndefined</td>
<td>Reservied for system use.</td>
</tr>

<tr>
<td>WdfIoTargetWaitForSentIoToComplete</td>
<td>Before the framework stops the I/O target, it will wait for I/O requests that are in the I/O target's queue to be completed. The framework completes all of the target queue's I/O requests, and calls each request's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556905">IRequestCallbackRequestCompletion::OnCompletion</a> callback function, before <a href="https://msdn.microsoft.com/library/windows/hardware/ff559217">IWDFIoTargetStateManagement::Stop</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff560289">IWDFRemoteTarget::Stop</a> returns.</td>
</tr>
</table>

## Remarks

The <b>WDF_IO_TARGET_SENT_IO_ACTION</b> enumeration is used as an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559217">IWDFIoTargetStateManagement::Stop</a> and  <a href="https://msdn.microsoft.com/library/windows/hardware/ff560289">IWDFRemoteTarget::Stop</a> methods.

If your driver specifies the <b>WdfIoTargetWaitForSentIoToComplete</b> flag, the driver must not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559217">IWDFIoTargetStateManagement::Stop</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff560289">IWDFRemoteTarget::Stop</a> from a request handler, an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556905">IRequestCallbackRequestCompletion::OnCompletion</a> callback function, or an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556915">IUsbTargetPipeContinuousReaderCallbackReadersFailed::OnReaderFailure</a> callback function.

For the KMDF version of this enumeration, see <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_target_sent_io_action.md">WDF_IO_TARGET_SENT_IO_ACTION</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** | 1.0 |
| **Header** | wudfddi_types.h (include Wudfddi.h) |

## See Also

<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_target_sent_io_action.md">WDF_IO_TARGET_SENT_IO_ACTION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_TARGET_SENT_IO_ACTION enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>