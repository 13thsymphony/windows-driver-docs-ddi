---
UID: NF:wdfusb.WdfUsbTargetDeviceSendControlTransferSynchronously
title: WdfUsbTargetDeviceSendControlTransferSynchronously function
author: windows-driver-content
description: The WdfUsbTargetDeviceSendControlTransferSynchronously method builds a USB control transfer request and sends it synchronously to an I/O target.
old-location: wdf\wdfusbtargetdevicesendcontroltransfersynchronously.htm
old-project: wdf
ms.assetid: 95150a1f-e323-4c29-8a4e-12ab4f231bc6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_fe154a84-e5b4-4997-ad1f-6eb7f6829553.xml, WdfUsbTargetDeviceSendControlTransferSynchronously, WdfUsbTargetDeviceSendControlTransferSynchronously method, kmdf.wdfusbtargetdevicesendcontroltransfersynchronously, wdf.wdfusbtargetdevicesendcontroltransfersynchronously, wdfusb/WdfUsbTargetDeviceSendControlTransferSynchronously
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfUsbTargetDeviceSendControlTransferSynchronously
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WdfUsbTargetDeviceSendControlTransferSynchronously function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> method builds a USB control transfer request and sends it synchronously to an I/O target.

## Syntax

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

## Parameters

`UsbDevice`

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.

`Request`

A handle to a framework request object. This parameter is optional and can be <b>NULL</b>. For more information, see the following Remarks section.

`RequestOptions`

A pointer to a caller-allocated <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure that specifies options for the request. This pointer is optional and can be <b>NULL</b>. For more information, see the following Remarks section.

`SetupPacket`

A pointer to a caller-allocated <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure that describes the control transfer.

`MemoryDescriptor`

A pointer to a caller-allocated <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure that describes either an input or an output buffer, depending on the device-specific command. This pointer is optional and can be <b>NULL</b>. For more information, see the following Remarks section.

`BytesTransferred`

A pointer to a location that receives the number of bytes that are transferred. This parameter is optional and can be <b>NULL</b>.


## Return Value

<b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> returns the I/O target's completion status value if the operation succeeds. Otherwise, this method can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
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
An invalid memory descriptor was specified, or the specified I/O request was already queued to an I/O target.

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
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

Use the <b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> method to send a USB control transfer request synchronously. To send such requests asynchronously, use <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforcontroltransfer.md">WdfUsbTargetDeviceFormatRequestForControlTransfer</a>, followed by <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>.

The <b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> method does not return until the request has completed, unless the driver supplies a time-out value in the <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure that the <i>RequestOptions</i> parameter points to, or unless an error is detected.

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request. In either case, the framework requires a request object and, depending on the type of control transfer, possibly some buffer space.

To forward an I/O request that your driver received in an I/O queue:

<ol>
<li>
Specify the received request's handle for the <i>Request</i> parameter.

</li>
<li>
Use the received request's input or output buffer for the <i>MemoryDescriptor</i> parameter.

The driver can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveinputmemory.md">WdfRequestRetrieveInputMemory</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a> to obtain a handle to a framework memory object that represents the request's input or output buffer and then place that handle in the <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure that the driver supplies for the <i>MemoryDescriptor</i> parameter.

</li>
</ol>
To create and send a new request:

<ol>
<li>
Supply a <b>NULL</b> request handle in the <i>Request</i> parameter, or create a new request object and supply its handle:<ul>
<li>If you supply a <b>NULL</b> request handle, the framework uses an internal request object. This technique is simple to use, but the driver cannot cancel the request.</li>
<li>If you call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a> to create one or more request objects, you can reuse these request objects by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>. This technique enables your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function to preallocate request objects for a device. Additionally, another driver thread can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcancelsentrequest.md">WdfRequestCancelSentRequest</a> to cancel the request, if necessary.</li>
</ul>


Your driver can specify a non-<b>NULL</b> <i>RequestOptions</i> parameter, whether the driver provides a non-<b>NULL</b> or a <b>NULL</b> <i>Request</i> parameter. You can, for example, use the <i>RequestOptions</i> parameter to specify a time-out value. 

</li>
<li>
Provide buffer space for the <b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> method's <i>MemoryDescriptor</i> parameter. 

Your driver can specify this buffer space as a locally allocated buffer, as a WDFMEMORY handle, or as an MDL. You can use whichever method is most convenient. 

If necessary, the framework converts the buffer description to one that is correct for the I/O target's <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">method for accessing data buffers</a>. 

The following techniques are available:

<ul>
<li>
Supply non-pageable resident buffers, e.g. non-paged pool 

**Note:** Kernel stack is not guaranteed to be resident.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_MEMORY_DESCRIPTOR  memoryDescriptor;
MY_BUFFER_TYPE  myBuffer;
WDF_MEMORY_DESCRIPTOR_INIT_BUFFER(&amp;memoryDescriptor,
                                  (PVOID) &amp;myBuffer,
                                  sizeof(myBuffer));</pre>
</td>
</tr>
</table></span></div>
</li>
<li>
Supply a WDFMEMORY handle

Call <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a> or <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatepreallocated.md">WdfMemoryCreatePreallocated</a> to obtain a handle to framework-managed memory, as shown in the following code example. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_MEMORY_DESCRIPTOR  memoryDescriptor;
WDFMEMORY  memoryHandle = NULL;
status = WdfMemoryCreate(NULL,
                         NonPagedPool,
                         POOL_TAG,
                         MY_BUFFER_SIZE,
                         &amp;memoryHandle,
                         NULL);
WDF_MEMORY_DESCRIPTOR_INIT_HANDLE(&amp;memoryDescriptor,
                                  memoryHandle,
                                  NULL);</pre>
</td>
</tr>
</table></span></div>
Alternatively, the driver can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveinputmemory.md">WdfRequestRetrieveInputMemory</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a> to obtain a handle to a framework memory object that represents a received I/O request's buffer, if you want the driver to pass that buffer's contents to the I/O target. The driver must not complete the received I/O request until the new request that <b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> sends to the I/O target has been deleted, reused, or reformatted. (<b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> increments the memory object's reference count. Deleting, reusing, or reformatting a request object decrements the memory object's reference count.)

</li>
<li>
Supply an MDL

Drivers can obtain MDLs that are associated with a received I/O request by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveinputwdmmdl.md">WdfRequestRetrieveInputWdmMdl</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputwdmmdl.md">WdfRequestRetrieveOutputWdmMdl</a>.

</li>
</ul>
</li>
</ol>
The framework sets the USBD_SHORT_TRANSFER_OK flag in its internal <a href="..\usb\ns-usb-_urb.md">URB</a>. Setting this flag allows the last packet of a data transfer to be less than the maximum packet size.

For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about the <b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example initializes a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure and then calls <b>WdfUsbTargetDeviceSendControlTransferSynchronously</b> to send a vendor-specific control transfer.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_USB_CONTROL_SETUP_PACKET  controlSetupPacket;

WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR(
                                         &amp;controlSetupPacket,
                                         BmRequestHostToDevice,
                                         BmRequestToDevice,
                                         USBFX2LK_REENUMERATE,
                                         0,
                                         0
                                         );

status = WdfUsbTargetDeviceSendControlTransferSynchronously(
                                         UsbDevice,
                                         WDF_NO_HANDLE,
                                         NULL,
                                         &amp;controlSetupPacket,
                                         NULL,
                                         NULL
                                         );
return status;</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2, RequestForUrbXrb, SyncReqSend, UsbKmdfIrql, UsbKmdfIrql2 |

## See Also

<a href="..\wdfusb\nf-wdfusb-wdf_usb_control_setup_packet_init_vendor.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcancelsentrequest.md">WdfRequestCancelSentRequest</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforcontroltransfer.md">WdfUsbTargetDeviceFormatRequestForControlTransfer</a>



<a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicesendurbsynchronously.md">WdfUsbTargetDeviceSendUrbSynchronously</a>