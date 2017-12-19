---
UID: NF.wdfusb.WdfUsbTargetDeviceSendControlTransferSynchronously
title: WdfUsbTargetDeviceSendControlTransferSynchronously function
author: windows-driver-content
description: The WdfUsbTargetDeviceSendControlTransferSynchronously method builds a USB control transfer request and sends it synchronously to an I/O target.
old-location: wdf\wdfusbtargetdevicesendcontroltransfersynchronously.htm
old-project: wdf
ms.assetid: 95150a1f-e323-4c29-8a4e-12ab4f231bc6
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WdfUsbTargetDeviceSendControlTransferSynchronously
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
req.alt-api: WdfUsbTargetDeviceSendControlTransferSynchronously
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, RequestForUrbXrb, SyncReqSend, UsbKmdfIrql, UsbKmdfIrql2
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

# WdfUsbTargetDeviceSendControlTransferSynchronously function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> method builds a USB control transfer request and sends it synchronously to an I/O target.



## -syntax

````
NTSTATUS WdfUsbTargetDeviceSendControlTransferSynchronously(
  _In_      WDFUSBDEVICE                  UsbDevice,
  _In_opt_  WDFREQUEST                    Request,
  _In_opt_  PWDF_REQUEST_SEND_OPTIONS     RequestOptions,
  _In_      PWDF_USB_CONTROL_SETUP_PACKET SetupPacket,
  _In_opt_  PWDF_MEMORY_DESCRIPTOR        MemoryDescriptor,
  _Out_opt_ PULONG                        BytesTransferred
);
````


## -parameters

### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="wdf.wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param Request [in, optional]

A handle to a framework request object. This parameter is optional and can be <b>NULL</b>. For more information, see the following Remarks section.


### -param RequestOptions [in, optional]

A pointer to a caller-allocated <a href="wdf.wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure that specifies options for the request. This pointer is optional and can be <b>NULL</b>. For more information, see the following Remarks section.


### -param SetupPacket [in]

A pointer to a caller-allocated <a href="wdf.wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure that describes the control transfer.


### -param MemoryDescriptor [in, optional]

A pointer to a caller-allocated <a href="wdf.wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure that describes either an input or an output buffer, depending on the device-specific command. This pointer is optional and can be <b>NULL</b>. For more information, see the following Remarks section.


### -param BytesTransferred [out, optional]

A pointer to a location that receives the number of bytes that are transferred. This parameter is optional and can be <b>NULL</b>.


## -returns
<b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> returns the I/O target's completion status value if the operation succeeds. Otherwise, this method can return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was detected.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Insufficient memory was available.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>An invalid memory descriptor was specified, or the specified I/O request was already queued to an I/O target.
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>The driver supplied a time-out value and the request did not complete within the allotted time. 

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
Use the <b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> method to send a USB control transfer request synchronously. To send such requests asynchronously, use <a href="wdf.wdfusbtargetdeviceformatrequestforcontroltransfer">WdfUsbTargetDeviceFormatRequestForControlTransfer</a>, followed by <a href="wdf.wdfrequestsend">WdfRequestSend</a>.

The <b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> method does not return until the request has completed, unless the driver supplies a time-out value in the <a href="wdf.wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure that the <i>RequestOptions</i> parameter points to, or unless an error is detected.

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request. In either case, the framework requires a request object and, depending on the type of control transfer, possibly some buffer space.

To forward an I/O request that your driver received in an I/O queue:

Specify the received request's handle for the <i>Request</i> parameter.

Use the received request's input or output buffer for the <i>MemoryDescriptor</i> parameter.

The driver can call <a href="wdf.wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a> or <a href="wdf.wdfrequestretrieveoutputmemory">WdfRequestRetrieveOutputMemory</a> to obtain a handle to a framework memory object that represents the request's input or output buffer and then place that handle in the <a href="wdf.wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure that the driver supplies for the <i>MemoryDescriptor</i> parameter.

To create and send a new request:

Supply a <b>NULL</b> request handle in the <i>Request</i> parameter, or create a new request object and supply its handle:<ul>
<li>If you supply a <b>NULL</b> request handle, the framework uses an internal request object. This technique is simple to use, but the driver cannot cancel the request.</li>
<li>If you call <a href="wdf.wdfrequestcreate">WdfRequestCreate</a> to create one or more request objects, you can reuse these request objects by calling <a href="wdf.wdfrequestreuse">WdfRequestReuse</a>. This technique enables your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function to preallocate request objects for a device. Additionally, another driver thread can call <a href="wdf.wdfrequestcancelsentrequest">WdfRequestCancelSentRequest</a> to cancel the request, if necessary.</li>
</ul>


Your driver can specify a non-<b>NULL</b> <i>RequestOptions</i> parameter, whether the driver provides a non-<b>NULL</b> or a <b>NULL</b> <i>Request</i> parameter. You can, for example, use the <i>RequestOptions</i> parameter to specify a time-out value. 

Provide buffer space for the <b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> method's <i>MemoryDescriptor</i> parameter. 

Your driver can specify this buffer space as a locally allocated buffer, as a WDFMEMORY handle, or as an MDL. You can use whichever method is most convenient. 

If necessary, the framework converts the buffer description to one that is correct for the I/O target's <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">method for accessing data buffers</a>. 

The following techniques are available:

Supply a local buffer

Because <b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> handles I/O requests synchronously, the driver can create request buffers that are local to the calling routine, as shown in the following code example.

Supply a WDFMEMORY handle

Call <a href="wdf.wdfmemorycreate">WdfMemoryCreate</a> or <a href="wdf.wdfmemorycreatepreallocated">WdfMemoryCreatePreallocated</a> to obtain a handle to framework-managed memory, as shown in the following code example. 

Alternatively, the driver can call <a href="wdf.wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a> or <a href="wdf.wdfrequestretrieveoutputmemory">WdfRequestRetrieveOutputMemory</a> to obtain a handle to a framework memory object that represents a received I/O request's buffer, if you want the driver to pass that buffer's contents to the I/O target. The driver must not complete the received I/O request until the new request that <b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> sends to the I/O target has been deleted, reused, or reformatted. (<b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> increments the memory object's reference count. Deleting, reusing, or reformatting a request object decrements the memory object's reference count.)

Supply an MDL

Drivers can obtain MDLs that are associated with a received I/O request by calling <a href="wdf.wdfrequestretrieveinputwdmmdl">WdfRequestRetrieveInputWdmMdl</a> or <a href="wdf.wdfrequestretrieveoutputwdmmdl">WdfRequestRetrieveOutputWdmMdl</a>.

The framework sets the USBD_SHORT_TRANSFER_OK flag in its internal <a href="buses.urb">URB</a>. Setting this flag allows the last packet of a data transfer to be less than the maximum packet size.

For information about obtaining status information after an I/O request completes, see <a href="wdf.completing_i_o_requests#obtaining_completion_information#obtaining_completion_information">Obtaining Completion Information</a>.

For more information about the <b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> method and USB I/O targets, see <a href="wdf.usb_i_o_targets">USB I/O Targets</a>.

The following code example initializes a <a href="wdf.wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure and then calls <b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> to send a vendor-specific control transfer.


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
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>, <a href="devtest.kmdf_requestforurbxrb">RequestForUrbXrb</a>, <a href="devtest.kmdf_syncreqsend">SyncReqSend</a>, <a href="devtest.kmdf_usbkmdfirql">UsbKmdfIrql</a>, <a href="devtest.kmdf_usbkmdfirql2">UsbKmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a>
</dt>
<dt>
<a href="wdf.wdf_usb_control_setup_packet_init_vendor">WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</a>
</dt>
<dt>
<a href="wdf.wdfrequestcancelsentrequest">WdfRequestCancelSentRequest</a>
</dt>
<dt>
<a href="wdf.wdfusbtargetdeviceformatrequestforcontroltransfer">WdfUsbTargetDeviceFormatRequestForControlTransfer</a>
</dt>
<dt>
<a href="wdf.wdfusbtargetdevicesendurbsynchronously">WdfUsbTargetDeviceSendUrbSynchronously</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceSendControlTransferSynchronously method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

