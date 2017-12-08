---
UID: NF.wdfusb.WdfUsbTargetPipeAbortSynchronously
title: WdfUsbTargetPipeAbortSynchronously function
author: windows-driver-content
description: The WdfUsbTargetPipeAbortSynchronously method builds an abort request and sends it synchronously to a specified USB pipe.
old-location: wdf\wdfusbtargetpipeabortsynchronously.htm
old-project: wdf
ms.assetid: 57d0969f-bc30-4235-93a5-dda51e15b4fc
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfUsbTargetPipeAbortSynchronously
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfUsbTargetPipeAbortSynchronously
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, RequestForUrbXrb, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# WdfUsbTargetPipeAbortSynchronously function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WdfUsbTargetPipeAbortSynchronously</b> method builds an abort request and sends it synchronously to a specified USB pipe.


## -syntax

````
NTSTATUS WdfUsbTargetPipeAbortSynchronously(
  _In_     WDFUSBPIPE                Pipe,
  _In_opt_ WDFREQUEST                Request,
  _In_opt_ PWDF_REQUEST_SEND_OPTIONS RequestOptions
);
````


## -parameters

### -param Pipe [in]

A handle to a framework pipe object that was obtained by calling <a href="wdf.wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>. 

### -param Request [in, optional]

A handle to a framework request object. This parameter is optional and can be <b>NULL</b>. For more information, see the following Remarks section.

### -param RequestOptions [in, optional]

A pointer to a caller-allocated <a href="wdf.wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure that specifies options for the request. This pointer is optional and can be <b>NULL</b>. For more information, see the following Remarks section.

## -returns
<b>WdfUsbTargetPipeAbortSynchronously</b> returns the I/O target's completion status value if the operation succeeds. Otherwise, this method can return one of the following values:
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The size of the <a href="wdf.wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure that the <i>RequestOptions</i> parameter specified was incorrect.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid handle was detected.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Insufficient memory was available.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The caller's IRQL was not PASSIVE_LEVEL, or the specified I/O request was already queued to an I/O target.
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>The driver supplied a time-out value and the request did not complete within the allotted time.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks
Use the <b>WdfUsbTargetPipeAbortSynchronously</b> method to send a USB abort request synchronously. To send such requests asynchronously, use <a href="wdf.wdfusbtargetpipeformatrequestforabort">WdfUsbTargetPipeFormatRequestForAbort</a>, followed by <a href="wdf.wdfrequestsend">WdfRequestSend</a>.

A USB abort request causes the driver's I/O target to cancel all of the I/O requests that have been sent to a pipe. When a driver calls <b>WdfUsbTargetPipeAbortSynchronously</b>, the framework sends a <a href="..\usb\ns-usb-_urb_header.md">URB_FUNCTION_ABORT_PIPE</a> request to the I/O target. For more information about canceling operations on a USB pipe (also called "aborting a pipe"), see the USB specification.

The <b>WdfUsbTargetPipeAbortSynchronously</b> method does not return until the request has completed, unless the driver supplies a time-out value in the <i>RequestOptions</i> parameter's <a href="wdf.wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure, or unless an error is detected.

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request.

To forward an I/O request that your driver received in an I/O queue, specify the received request's handle for the <b>WdfUsbTargetPipeAbortSynchronously</b> method's <i>Request</i> parameter.

To create and send a new request, either supply a <b>NULL</b> request handle for the <i>Request</i> parameter, or create a new request object and supply its handle:

If you supply a <b>NULL</b> request handle, the framework uses an internal request object. This technique is simple to use, but the driver cannot cancel the request.

If you call <a href="wdf.wdfrequestcreate">WdfRequestCreate</a> to create one or more request objects, you can reuse these request objects by calling <a href="wdf.wdfrequestreuse">WdfRequestReuse</a>. This technique enables your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function to preallocate request objects for a device. Additionally, another driver thread can call <a href="wdf.wdfrequestcancelsentrequest">WdfRequestCancelSentRequest</a> to cancel the request, if necessary.

Your driver can specify a non-<b>NULL</b> <i>RequestOptions</i> parameter, whether the driver provides a non-<b>NULL</b> or a <b>NULL</b> <i>Request</i> parameter. You can, for example, use the <i>RequestOptions</i> parameter to specify a time-out value. 

For information about obtaining status information after an I/O request completes, see <a href="wdf.completing_i_o_requests#obtaining_completion_information#obtaining_completion_information">Obtaining Completion Information</a>.

For more information about the <b>WdfUsbTargetPipeAbortSynchronously</b> method and USB I/O targets, see <a href="wdf.usb_i_o_targets">USB I/O Targets</a>.

The following code example sends abort requests to all of the pipes that are configured for a USB device's interface.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfusb.h (include Wdfusb.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>, <a href="devtest.kmdf_requestforurbxrb">RequestForUrbXrb</a>, <a href="devtest.kmdf_usbkmdfirql">UsbKmdfIrql</a>, <a href="devtest.kmdf_usbkmdfirql2">UsbKmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfusbtargetpiperesetsynchronously">WdfUsbTargetPipeResetSynchronously</a>
</dt>
<dt>
<a href="wdf.wdfrequestcancelsentrequest">WdfRequestCancelSentRequest</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetPipeAbortSynchronously method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
