---
UID: NS:usb._URB_HEADER
title: _URB_HEADER
author: windows-driver-content
description: The _URB_HEADER structure is used by USB client drivers to provide basic information about the request being sent to the host controller driver.
old-location: buses\_urb_header.htm
old-project: usbref
ms.assetid: d23b9332-1e9d-4592-9674-3e5d8fc1d11e
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _URB_HEADER,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usb.h
req.include-header: Usb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: _URB_HEADER
req.alt-loc: usb.h
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
req.typenames: 
req.product: Windows 10 or later.
---

# _URB_HEADER structure



## -description
The <b>_URB_HEADER</b> structure is used by USB client drivers to provide basic information about the request being sent to the host controller driver.



## -syntax

````
struct _URB_HEADER {
  USHORT      Length;
  USHORT      Function;
  USBD_STATUS Status;
  PVOID       UsbdDeviceHandle;
  ULONG       UsbdFlags;
};
````


## -struct-fields

### -field Length

Specifies the length, in bytes, of the URB. For URB requests that use data structures other than <b>_URB_HEADER</b>, this member must be set to the length of the entire URB request structure, not the _URB_HEADER size.


### -field Function


Specifies a numeric code indicating the requested operation for this URB. One of the following values must be set:




### -field URB_FUNCTION_SELECT_CONFIGURATION

<dd>
Indicates to the host controller driver that a configuration is to be selected. If set, the URB is used with <a href="..\usb\ns-usb-_urb_select_configuration.md">_URB_SELECT_CONFIGURATION</a> as the data structure.


### -field URB_FUNCTION_SELECT_INTERFACE

<dd>
Indicates to the host controller driver that an alternate interface setting is being selected for an interface. If set, the URB is used with <a href="..\usb\ns-usb-_urb_select_interface.md">_URB_SELECT_INTERFACE</a> as the data structure. 


### -field URB_FUNCTION_ABORT_PIPE

<dd>
Indicates that all outstanding requests for a pipe should be canceled. If set, the URB is used with <a href="..\usb\ns-usb-_urb_pipe_request.md">_URB_PIPE_REQUEST</a> as the data structure. This general-purpose request enables a client to cancel any pending transfers for the specified pipe. Pipe state and endpoint state are unaffected. The abort request might complete before all outstanding requests have completed. Do <i>not</i> assume that completion of the abort request implies that all other outstanding requests have completed. 


### -field URB_FUNCTION_TAKE_FRAME_LENGTH_CONTROL

<dd>
This URB function is <b>deprecated</b> in Windows 2000 and later operating systems and is not supported by Microsoft. Do not use. If you specify this function with an URB request, the request will fail and the system will report an error. 


### -field URB_FUNCTION_RELEASE_FRAME_LENGTH_CONTROL

<dd>
This URB function is <b>deprecated</b> in Windows 2000 and later operating systems and is not supported by Microsoft. Do not use. If you specify this function with an URB request, the request will fail and the system will report an error. 


### -field URB_FUNCTION_GET_FRAME_LENGTH

<dd>
This URB function is <b>deprecated</b> in Windows 2000 and later operating systems and is not supported by Microsoft. Do not use.  If you use this function with a URB request, the request will fail and the system will report an error.


### -field URB_FUNCTION_SET_FRAME_LENGTH

<dd>
This URB function is <b>deprecated</b> in Windows 2000 and later operating systems and is not supported by Microsoft. Do not use.  If you use it with a URB request, the request will fail and the system will report an error. 


### -field URB_FUNCTION_GET_CURRENT_FRAME_NUMBER

<dd>
Requests the current frame number from the host controller driver. If set, the URB is used with <a href="..\usb\ns-usb-_urb_get_current_frame_number.md">_URB_GET_CURRENT_FRAME_NUMBER</a> as the data structure. 


### -field URB_FUNCTION_CONTROL_TRANSFER

<dd>
Transfers data to or from a control pipe. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_transfer.md">_URB_CONTROL_TRANSFER</a> as the data structure. 


### -field URB_FUNCTION_CONTROL_TRANSFER_EX

<dd>
Transfers data to or from a control pipe without a time limit specified by a timeout value. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_transfer_ex.md">URB_CONTROL_TRANSFER_EX</a> as the data structure. 

Available in Windows Vista and later operating systems.



### -field URB_FUNCTION_BULK_OR_INTERRUPT_TRANSFER

<dd>
Transfers data from a bulk pipe or interrupt pipe or to an bulk pipe. If set, the URB is used with <a href="..\usb\ns-usb-_urb_bulk_or_interrupt_transfer.md">_URB_BULK_OR_INTERRUPT_TRANSFER</a> as the data structure. 


### -field URB_FUNCTION_BULK_OR_INTERRUPT_TRANSFER_USING_CHAINED_MDL

<dd>
Transfers data to and from a bulk pipe or interrupt pipe, by using chained MDLs. If set, the URB is used with <a href="..\usb\ns-usb-_urb_bulk_or_interrupt_transfer.md">_URB_BULK_OR_INTERRUPT_TRANSFER</a> as the data structure. The client driver must set the <b>TransferBufferMDL</b>  member to the first <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> structure in the chain that contains the transfer buffer. The USB driver stack ignores the <b>TransferBuffer</b> member when processing this URB.

Available in Windows 8.  For information about using chained MDLs, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450848">How to Send Chained MDLs</a>.


### -field URB_FUNCTION_ISOCH_TRANSFER

<dd>
Transfers data to or from an isochronous pipe. If set, the URB is used with <a href="..\usb\ns-usb-_urb_isoch_transfer.md">_URB_ISOCH_TRANSFER</a> as the data structure.


### -field URB_FUNCTION_ISOCH_TRANSFER_USING_CHAINED_MDL

<dd>
Transfers data to or from an isochronous pipe by using chained MDLs. If set, the URB is used with <a href="..\usb\ns-usb-_urb_isoch_transfer.md">_URB_ISOCH_TRANSFER</a> as the data structure. The client driver must set the <b>TransferBufferMDL</b>  member to the first <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> in the chain that contains the transfer buffer. The USB driver stack ignores the <b>TransferBuffer</b> member when processing this URB.

Available in Windows 8.  For information about using chained MDLs, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450848">How to Send Chained MDLs</a>.


### -field URB_FUNCTION_RESET_PIPE

<dd>
See URB_FUNCTION_SYNC_RESET_PIPE_AND_CLEAR_STALL.


### -field URB_FUNCTION_SYNC_RESET_PIPE_AND_CLEAR_STALL

<dd>
Resets the indicated pipe. If set, this URB is used with <a href="..\usb\ns-usb-_urb_pipe_request.md">_URB_PIPE_REQUEST</a>.

<div class="alert"><b>Note</b>  This URB replaces URB_FUNCTION_RESET_PIPE.</div>
<div> </div>
The bus driver accomplishes three tasks in response to this URB:

First, for all pipes except isochronous pipes, this URB sends a CLEAR_FEATURE request to clear the device's ENDPOINT_HALT feature. 

Second, the USB bus driver resets the data toggle on the host side, as required by the USB specification. The USB device should reset the data toggle on the device side when the bus driver clears its ENDPOINT_HALT feature. Since some non-compliant devices do not support this feature, Microsoft provides the two additional URBs: URB_FUNCTION_SYNC_CLEAR_STALL and URB_FUNCTION_SYNC_RESET_PIPE. These allow client drivers to clear the ENDPOINT_HALT feature on the device, or reset the pipe on the host side, respectively, without affecting the data toggle on the host side. If the device does not reset the data toggle when it should, then the client driver can compensate for this defect by not resetting the host-side data toggle. If the data toggle is reset on the host side but not on the device side, packets will get out of sequence, and the device might drop packets. 

Third, after the bus driver has successfully reset the pipe, it resumes transfers with the next queued URB. 

After a pipe reset, transfers resume with the next queued URB.

It is not necessary to clear a halt condition on a default control pipe. The default control pipe must always accept setup packets, and so if it halts, the USB stack will clear the halt condition automatically. The client driver does not need to take any special action to clear the halt condition on a default pipe. 

All transfers must be aborted or canceled before attempting to reset the pipe.

This URB must be sent at PASSIVE_LEVEL.  


### -field URB_FUNCTION_SYNC_RESET_PIPE

<dd>
Clears the halt condition on the host side of a pipe. If set, this URB is used with <a href="..\usb\ns-usb-_urb_pipe_request.md">_URB_PIPE_REQUEST</a> as the data structure.

This URB allows a client to clear the halted state of a pipe without resetting the data toggle and without clearing the endpoint stall condition (feature ENDPOINT_HALT). To clear a halt condition on the pipe, reset the host-side data toggle and clear a stall on the device with a single operation, use URB_FUNCTION_SYNC_RESET_PIPE_AND_CLEAR_STALL.

The following status codes are important and have the indicated meaning:

    USBD_STATUS_INVALID_PIPE_HANDLE

        The <b>PipeHandle</b> is not valid

    USBD_STATUS_ERROR_BUSY

        The endpoint has active transfers pending.  

It is not necessary to clear a halt condition on a default control pipe. The default control pipe must always accept setup packets, and so if it halts, the USB stack will clear the halt condition automatically. The client driver does not need to take any special action to clear the halt condition on a default pipe. 

All transfers must be aborted or canceled before attempting to reset the pipe.

This URB must be sent at PASSIVE_LEVEL.  

Available in Windows XP and later operating systems.


### -field URB_FUNCTION_SYNC_CLEAR_STALL

<dd>
Clears the stall condition on the endpoint. For all pipes except isochronous pipes, this URB sends a CLEAR_FEATURE request to clear the device's ENDPOINT_HALT feature. However, unlike the URB_FUNCTION_SYNC_RESET_PIPE_AND_CLEAR_STALL function, this URB function does not reset the data toggle on the host side of the pipe. The USB specification requires devices to reset the device-side data toggle after the client clears the device's ENDPOINT_HALT feature, but some non-compliant devices do not reset their data toggle properly. Client drivers that manage such devices can compensate for this defect by clearing the stall condition directly with URB_FUNCTION_SYNC_CLEAR_STALL instead of resetting the pipe with URB_FUNCTION_SYNC_RESET_PIPE_AND_CLEAR_STALL. URB_FUNCTION_SYNC_CLEAR_STALL clears a stall condition on the device without resetting the host-side data toggle. This prevents a non-compliant device from interpreting the next packet as a retransmission and dropping the packet. 

If set, the URB is used with <a href="..\usb\ns-usb-_urb_pipe_request.md">_URB_PIPE_REQUEST</a> as the data structure. 

This URB function should be sent at PASSIVE_LEVEL

Available in Windows XP and later operating systems.


### -field URB_FUNCTION_GET_DESCRIPTOR_FROM_DEVICE

<dd>
Retrieves the device descriptor from a specific USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_descriptor_request.md">_URB_CONTROL_DESCRIPTOR_REQUEST</a> as the data structure. 


### -field URB_FUNCTION_GET_DESCRIPTOR_FROM_ENDPOINT

<dd>
Retrieves the descriptor from an endpoint on an interface for a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_descriptor_request.md">_URB_CONTROL_DESCRIPTOR_REQUEST</a> as the data structure.


### -field URB_FUNCTION_SET_DESCRIPTOR_TO_DEVICE

<dd>
Sets a device descriptor on a device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_descriptor_request.md">_URB_CONTROL_DESCRIPTOR_REQUEST</a> as the data structure.


### -field URB_FUNCTION_SET_DESCRIPTOR_TO_ENDPOINT

<dd>
Sets an endpoint descriptor on an endpoint for an interface. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_descriptor_request.md">_URB_CONTROL_DESCRIPTOR_REQUEST</a> as the data structure.


### -field URB_FUNCTION_SET_FEATURE_TO_DEVICE

<dd>
Sets a USB-defined feature on a device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_feature_request.md">_URB_CONTROL_FEATURE_REQUEST</a> as the data structure.


### -field URB_FUNCTION_SET_FEATURE_TO_INTERFACE

<dd>
Sets a USB-defined feature on an interface for a device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_feature_request.md">_URB_CONTROL_FEATURE_REQUEST</a> as the data structure.


### -field URB_FUNCTION_SET_FEATURE_TO_ENDPOINT

<dd>
Sets a USB-defined feature on an endpoint for an interface on a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_feature_request.md">_URB_CONTROL_FEATURE_REQUEST</a> as the data structure.


### -field URB_FUNCTION_SET_FEATURE_TO_OTHER

<dd>
Sets a USB-defined feature on a device-defined target on a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_feature_request.md">_URB_CONTROL_FEATURE_REQUEST</a> as the data structure.


### -field URB_FUNCTION_CLEAR_FEATURE_TO_DEVICE

<dd>
Clears a USB-defined feature on a device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_feature_request.md">_URB_CONTROL_FEATURE_REQUEST</a> as the data structure.


### -field URB_FUNCTION_CLEAR_FEATURE_TO_INTERFACE

<dd>
Clears a USB-defined feature on an interface for a device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_feature_request.md">_URB_CONTROL_FEATURE_REQUEST</a> as the data structure.


### -field URB_FUNCTION_CLEAR_FEATURE_TO_ENDPOINT

<dd>
Clears a USB-defined feature on an endpoint, for an interface, on a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_feature_request.md">_URB_CONTROL_FEATURE_REQUEST</a> as the data structure.


### -field URB_FUNCTION_CLEAR_FEATURE_TO_OTHER

<dd>
Clears a USB-defined feature on a device defined target on a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_feature_request.md">_URB_CONTROL_FEATURE_REQUEST</a> as the data structure.


### -field URB_FUNCTION_GET_STATUS_FROM_DEVICE

<dd>
Retrieves status from a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_get_status_request.md">_URB_CONTROL_GET_STATUS_REQUEST</a> as the data structure.


### -field URB_FUNCTION_GET_STATUS_FROM_INTERFACE

<dd>
Retrieves status from an interface on a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_get_status_request.md">_URB_CONTROL_GET_STATUS_REQUEST</a> as the data structure.


### -field URB_FUNCTION_GET_STATUS_FROM_ENDPOINT

<dd>
Retrieves status from an endpoint for an interface on a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_get_status_request.md">_URB_CONTROL_GET_STATUS_REQUEST</a> as the data structure.


### -field URB_FUNCTION_GET_STATUS_FROM_OTHER

<dd>
Retrieves status from a device-defined target on a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_get_status_request.md">_URB_CONTROL_GET_STATUS_REQUEST</a> as the data structure.


### -field URB_FUNCTION_VENDOR_DEVICE

<dd>
Sends a vendor-specific command to a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_vendor_or_class_request.md">_URB_CONTROL_VENDOR_OR_CLASS_REQUEST</a> as the data structure.


### -field URB_FUNCTION_VENDOR_INTERFACE

<dd>
Sends a vendor-specific command for an interface on a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_vendor_or_class_request.md">_URB_CONTROL_VENDOR_OR_CLASS_REQUEST</a> as the data structure.


### -field URB_FUNCTION_VENDOR_ENDPOINT

<dd>
Sends a vendor-specific command for an endpoint on an interface on a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_vendor_or_class_request.md">_URB_CONTROL_VENDOR_OR_CLASS_REQUEST</a> as the data structure.


### -field URB_FUNCTION_VENDOR_OTHER

<dd>
Sends a vendor-specific command to a device-defined target on a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_vendor_or_class_request.md">_URB_CONTROL_VENDOR_OR_CLASS_REQUEST</a> as the data structure.


### -field URB_FUNCTION_CLASS_DEVICE

<dd>
Sends a USB-defined class-specific command to a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_vendor_or_class_request.md">_URB_CONTROL_VENDOR_OR_CLASS_REQUEST</a> as the data structure.


### -field URB_FUNCTION_CLASS_INTERFACE

<dd>
Sends a USB-defined class-specific command to an interface on a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_vendor_or_class_request.md">_URB_CONTROL_VENDOR_OR_CLASS_REQUEST</a> as the data structure.


### -field URB_FUNCTION_CLASS_ENDPOINT

<dd>
Sends a USB-defined class-specific command to an endpoint, on an interface, on a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_vendor_or_class_request.md">_URB_CONTROL_VENDOR_OR_CLASS_REQUEST</a> as the data structure.


### -field URB_FUNCTION_CLASS_OTHER

<dd>
Sends a USB-defined class-specific command to a device defined target on a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_vendor_or_class_request.md">_URB_CONTROL_VENDOR_OR_CLASS_REQUEST</a> as the data structure.


### -field URB_FUNCTION_GET_CONFIGURATION

<dd>
Retrieves the current configuration on a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_get_configuration_request.md">_URB_CONTROL_GET_CONFIGURATION_REQUEST</a> as the data structure.


### -field URB_FUNCTION_GET_INTERFACE

<dd>
Retrieves the current settings for an interface on a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_get_interface_request.md">_URB_CONTROL_GET_INTERFACE_REQUEST</a> as the data structure.

Available in Windows 2000, and Windows Vista and later operating systems.  Not available in Windows XP.


### -field URB_FUNCTION_GET_DESCRIPTOR_FROM_INTERFACE

<dd>
Retrieves the descriptor from an interface for a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_descriptor_request.md">_URB_CONTROL_DESCRIPTOR_REQUEST</a> as the data structure.


### -field URB_FUNCTION_SET_DESCRIPTOR_TO_INTERFACE

<dd>
Sets a descriptor for an interface on a USB device. If set, the URB is used with <a href="..\usb\ns-usb-_urb_control_descriptor_request.md">_URB_CONTROL_DESCRIPTOR_REQUEST</a> as the data structure.


### -field URB_FUNCTION_GET_MS_FEATURE_DESCRIPTOR

<dd>
Retrieves a Microsoft OS feature descriptor from a USB device or an interface on a USB device.  If set, the URB is used with <a href="..\usb\ns-usb-_urb_os_feature_descriptor_request.md">_URB_OS_FEATURE_DESCRIPTOR_REQUEST</a>
as the data structure. 

Available in Windows XP and later operation systems.



### -field URB_FUNCTION_OPEN_STATIC_STREAMS  

<dd>
Opens streams in the specified bulk endpoint. If set, the URB is used with  <a href="..\usb\ns-usb-_urb_open_static_streams.md">_URB_OPEN_STATIC_STREAMS</a> as the data structure.

Available in Windows 8.  For information about formatting an URB for an open-stream request, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450846">How to Open and Close Static Streams in a USB Bulk Endpoint</a>.


### -field URB_FUNCTION_CLOSE_STATIC_STREAMS  

<dd>
Closes all opened streams in the specified bulk endpoint. If set, the URB is used with  <a href="..\usb\ns-usb-_urb_pipe_request.md">_URB_PIPE_REQUEST</a>  as the data structure.

Available in Windows 8. For information about formatting an URB for a close-stream request, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450846">How to Open and Close Static Streams in a USB Bulk Endpoint</a>.

</dd>
</dl>

### -field Status

Contains a USBD_STATUS_<i>XXX</i> code on return from the host controller driver.


### -field UsbdDeviceHandle

Reserved. Do not use.


### -field UsbdFlags

Reserved. Do not use.


## -remarks
The <b>_URB_HEADER</b> structure is a member of all USB requests that are part of the URB structure. The <b>_URB_HEADER</b> structure is used to provide common information about each request to the host controller driver.

The reserved members of this structure must be treated as opaque and are reserved for system use.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usb.h (include Usb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\usb\ns-usb-_urb.md">URB</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_select_interface.md">_URB_SELECT_INTERFACE</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_select_configuration.md">_URB_SELECT_CONFIGURATION</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_pipe_request.md">_URB_PIPE_REQUEST</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_get_current_frame_number.md">_URB_GET_CURRENT_FRAME_NUMBER</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_control_transfer.md">_URB_CONTROL_TRANSFER</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_bulk_or_interrupt_transfer.md">_URB_BULK_OR_INTERRUPT_TRANSFER</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_isoch_transfer.md">_URB_ISOCH_TRANSFER</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_control_descriptor_request.md">_URB_CONTROL_DESCRIPTOR_REQUEST</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_control_get_status_request.md">_URB_CONTROL_GET_STATUS_REQUEST</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_control_feature_request.md">_URB_CONTROL_FEATURE_REQUEST</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_control_vendor_or_class_request.md">_URB_CONTROL_VENDOR_OR_CLASS_REQUEST</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_control_get_interface_request.md">_URB_CONTROL_GET_INTERFACE_REQUEST</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_control_get_configuration_request.md">_URB_CONTROL_GET_CONFIGURATION_REQUEST</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_os_feature_descriptor_request.md">_URB_OS_FEATURE_DESCRIPTOR_REQUEST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20_URB_HEADER structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

