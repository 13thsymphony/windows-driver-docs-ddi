---
UID : NF:wdfusb.WdfUsbTargetPipeResetSynchronously
title : WdfUsbTargetPipeResetSynchronously function
author : windows-driver-content
description : The WdfUsbTargetPipeResetSynchronously method builds a reset request and sends it synchronously to a specified USB pipe.
old-location : wdf\wdfusbtargetpiperesetsynchronously.htm
old-project : wdf
ms.assetid : 7d29fb09-0ddc-4b61-8f85-c0e69d891bc5
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdfusb/WdfUsbTargetPipeResetSynchronously, DFUsbRef_07fcbce0-9754-49c9-988b-0875242739a0.xml, WdfUsbTargetPipeResetSynchronously, kmdf.wdfusbtargetpiperesetsynchronously, PFN_WDFUSBTARGETPIPERESETSYNCHRONOUSLY, wdf.wdfusbtargetpiperesetsynchronously, WdfUsbTargetPipeResetSynchronously method
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfusb.h
req.include-header : Wdfusb.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2, RequestForUrbXrb, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product : Windows 10 or later.
---


# WdfUsbTargetPipeResetSynchronously function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetPipeResetSynchronously</b> method builds a reset request and sends it synchronously to a specified USB pipe.

## Syntax

````
NTSTATUS WdfUsbTargetPipeResetSynchronously(
  _In_     WDFUSBPIPE                Pipe,
  _In_opt_ WDFREQUEST                Request,
  _In_opt_ PWDF_REQUEST_SEND_OPTIONS RequestOptions
);
````

## Parameters

`Pipe`

A handle to a framework pipe object that was obtained by calling <a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>.

`Request`

A handle to a framework request object. This parameter is optional and can be <b>NULL</b>. For more information, see the following Remarks section.

`RequestOptions`

A pointer to a caller-allocated <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure that specifies options for the request. This pointer is optional and can be <b>NULL</b>. For more information, see the following Remarks section.


## Return Value

<b>WdfUsbTargetPipeResetSynchronously</b> returns the USB I/O target's completion status value if the operation succeeds. Otherwise, this method can return one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure that the <i>RequestOptions</i> parameter specified was incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient memory was available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The caller's IRQL was not PASSIVE_LEVEL, or the I/O request that the <i>Request</i> parameter specified was already queued to an I/O target.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
The driver supplied a time-out value and the request did not complete within the allotted time. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REQUEST_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The I/O request packet (<a href="..\wdm\ns-wdm-_irp.md">IRP</a>) that the <i>Request</i> parameter represents does not provide enough <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structures to allow the driver to forward the request.

</td>
</tr>
</table> 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

Use the <b>WdfUsbTargetPipeResetSynchronously</b> method to send a USB reset request synchronously. To send such requests asynchronously use <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeformatrequestforreset.md">WdfUsbTargetPipeFormatRequestForReset</a>, followed by <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>.

Before the framework resets the I/O target's USB pipe, it cancels all I/O requests that remain in the I/O target's queue. The driver must not send additional I/O requests to the I/O target until <b>WdfUsbTargetPipeResetSynchronously</b> returns.

The driver must call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstop.md">WdfIoTargetStop</a> before it calls <b>WdfUsbTargetPipeResetSynchronously</b>. After <b>WdfUsbTargetPipeResetSynchronously</b> returns, the driver can call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstart.md">WdfIoTargetStart</a>.

When a driver calls <b>WdfUsbTargetPipeResetSynchronously</b>, the framework sends a <a href="..\usb\ns-usb-_urb_header.md">URB_FUNCTION_RESET_PIPE</a> request to the I/O target. For more information about resetting a USB pipe, see the USB specification.

The <b>WdfUsbTargetPipeResetSynchronously</b> method does not return until the request has completed, unless the driver supplies a time-out value in the <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure that the <i>RequestOptions</i> parameter points to, or unless an error is detected.

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request.

To forward an I/O request that your driver received in an I/O queue, specify the received request's handle for the <b>WdfUsbTargetPipeResetSynchronously</b> method's <i>Request</i> parameter.

To create and send a new request, either supply a <b>NULL</b> request handle for the <i>Request</i> parameter, or create a new request object and supply its handle:
<ul>
<li>
If you supply a <b>NULL</b> request handle, the framework uses an internal request object. This technique is simple to use, but the driver cannot cancel the request.

</li>
<li>
If you call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a> to create one or more request objects, you can reuse these request objects by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>. This technique enables your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function to preallocate request objects for a device. Additionally, another driver thread can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcancelsentrequest.md">WdfRequestCancelSentRequest</a> to cancel the request, if necessary.

</li>
</ul>Your driver can specify a non-<b>NULL</b> <i>RequestOptions</i> parameter, whether the driver provides a non-<b>NULL</b> or a <b>NULL</b> <i>Request</i> parameter. You can, for example, use the <i>RequestOptions</i> parameter to specify a time-out value. 

For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about the <b>WdfUsbTargetPipeResetSynchronously</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2, RequestForUrbXrb, UsbKmdfIrql, UsbKmdfIrql2 |

## See Also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548739">WdfObjectDereference</a>

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeabortsynchronously.md">WdfUsbTargetPipeAbortSynchronously</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcancelsentrequest.md">WdfRequestCancelSentRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetPipeResetSynchronously method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>