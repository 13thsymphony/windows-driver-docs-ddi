---
UID: NS.USB._URB
title: _URB
author: windows-driver-content
description: The URB structure is used by USB client drivers to describe USB request blocks (URBs) that send requests to the USB driver stack. The URB structure defines a format for all possible commands that can be sent to a USB device.
old-location: buses\urb.htm
old-project: usbref
ms.assetid: f28b2c97-61ee-4843-b3c5-b3a55f172c50
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _URB, URB, *PURB
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
req.alt-api: URB
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
req.product: Windows 10 or later.
---

# _URB structure



## -description
The <b>URB</b> structure is used by USB client drivers to describe USB request blocks (URBs) that send requests to the USB driver stack. The <b>URB</b> structure defines a format for all possible commands that can be sent to a USB device.



## -syntax

````
typedef struct _URB {
  union {
    struct _URB_HEADER  UrbHeader;
    struct _URB_SELECT_INTERFACE  UrbSelectInterface;
    struct _URB_SELECT_CONFIGURATION  UrbSelectConfiguration;
    struct _URB_PIPE_REQUEST  UrbPipeRequest;
    struct _URB_FRAME_LENGTH_CONTROL  UrbFrameLengthControl;
    struct _URB_GET_FRAME_LENGTH  UrbGetFrameLength;
    struct _URB_SET_FRAME_LENGTH  UrbSetFrameLength;
    struct _URB_GET_CURRENT_FRAME_NUMBER  UrbGetCurrentFrameNumber;
    struct _URB_CONTROL_TRANSFER  UrbControlTransfer;
    struct _URB_CONTROL_TRANSFER_EX  UrbControlTransferEx;
    struct _URB_CONTROL_TRANSFER_EX  UrbControlTransferEx;
    struct _URB_BULK_OR_INTERRUPT_TRANSFER  UrbBulkOrInterruptTransfer;
    struct _URB_ISOCH_TRANSFER  UrbIsochronousTransfer;
    struct _URB_CONTROL_DESCRIPTOR_REQUEST  UrbControlDescriptorRequest;
    struct _URB_CONTROL_GET_STATUS_REQUEST  UrbControlGetStatusRequest;
    struct _URB_CONTROL_FEATURE_REQUEST  UrbControlFeatureRequest;
    struct _URB_CONTROL_VENDOR_OR_CLASS_REQUEST  UrbControlVendorClassRequest;
    struct _URB_CONTROL_GET_INTERFACE_REQUEST  UrbControlGetInterfaceRequest;
    struct _URB_CONTROL_GET_CONFIGURATION_REQUEST  UrbControlGetConfigurationRequest;
    struct _URB_OS_FEATURE_DESCRIPTOR_REQUEST  UrbOSFeatureDescriptorRequest;
    struct _URB_OPEN_STATIC_STREAMS  UrbOpenStaticStreams;
    struct _URB_GET_ISOCH_PIPE_TRANSFER_PATH_DELAYS  UrbGetIsochPipeTransferPathDelays;
  };
} URB, *PURB;
````


## -struct-fields

### -field UrbHeader

Provides basic information about the request being sent to the host controller driver. For more information, see <a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a>.


### -field UrbSelectInterface

Defines the format of a select interface command for a USB device. For more information, see <a href="..\usb\ns-usb-_urb_select_interface.md">_URB_SELECT_INTERFACE</a>.


### -field UrbSelectConfiguration

Defines the format of a select configuration command for a USB device. For more information, see <a href="..\usb\ns-usb-_urb_select_configuration.md">_URB_SELECT_CONFIGURATION</a>.


### -field UrbPipeRequest

Defines the format for a command for a  pipe in a USB endpoint. For more information, see <a href="..\usb\ns-usb-_urb_pipe_request.md">_URB_PIPE_REQUEST</a>.


### -field UrbFrameLengthControl

Deprecated in Windows 2000 and later operating systems and is not supported by Microsoft. Do not use. 


### -field UrbGetFrameLength

Deprecated in Windows 2000 and later operating systems and is not supported by Microsoft. Do not use. 


### -field UrbSetFrameLength

Deprecated in Windows 2000 and later operating systems and is not supported by Microsoft. Do not use. 


### -field UrbGetCurrentFrameNumber

Defines the format for a command to get the current frame number on a USB bus. For more information, see <a href="..\usb\ns-usb-_urb_get_current_frame_number.md">_URB_GET_CURRENT_FRAME_NUMBER</a>.


### -field UrbControlTransfer

Defines the format for a command to transmit or receive data on a control pipe. For more information, see <a href="..\usb\ns-usb-_urb_control_transfer.md">_URB_CONTROL_TRANSFER</a>.


### -field UrbControlTransferEx

Defines the format for a command to transmit or receive data on a control pipe. For more information, see <a href="..\usb\ns-usb-_urb_control_transfer_ex.md">_URB_CONTROL_TRANSFER_EX</a>.


### -field UrbControlTransferEx

Defines the format for a command to transmit or receive data on a control pipe. 


### -field UrbBulkOrInterruptTransfer

Defines the format for a command to transmit or receive data on a bulk pipe, or to receive data from an interrupt pipe. For more information, see <a href="..\usb\ns-usb-_urb_bulk_or_interrupt_transfer.md">_URB_BULK_OR_INTERRUPT_TRANSFER</a>.


### -field UrbIsochronousTransfer

Defines the format of an isochronous transfer to a USB device. For more information, see <a href="..\usb\ns-usb-_urb_isoch_transfer.md">_URB_ISOCH_TRANSFER</a>.


### -field UrbControlDescriptorRequest

Defines the format for a command to retrieve or set descriptor(s) on a USB device. For more information, see <a href="..\usb\ns-usb-_urb_control_descriptor_request.md">_URB_CONTROL_DESCRIPTOR_REQUEST</a>.


### -field UrbControlGetStatusRequest

Defines the format for a command to get status from a device, interface, or endpoint. For more information, see <a href="..\usb\ns-usb-_urb_control_get_status_request.md">_URB_CONTROL_GET_STATUS_REQUEST</a>.


### -field UrbControlFeatureRequest

Defines the format for a command to set or clear USB-defined features on an device, interface, or endpoint. For more information, see <a href="..\usb\ns-usb-_urb_control_feature_request.md">_URB_CONTROL_FEATURE_REQUEST</a>.


### -field UrbControlVendorClassRequest

Defines the format for a command to send or receive a vendor or class-specific request on a device, interface, endpoint, or other device-defined target. For more information, see <a href="..\usb\ns-usb-_urb_control_vendor_or_class_request.md">_URB_CONTROL_VENDOR_OR_CLASS_REQUEST</a>.


### -field UrbControlGetInterfaceRequest

Defines the format for a command to get the current alternate interface setting for a selected interface. For more information, see <a href="..\usb\ns-usb-_urb_control_get_interface_request.md">_URB_CONTROL_GET_INTERFACE_REQUEST</a>.


### -field UrbControlGetConfigurationRequest

Defines the format for a command to get the current configuration for a device. For more information, see <a href="..\usb\ns-usb-_urb_control_get_configuration_request.md">_URB_CONTROL_GET_CONFIGURATION_REQUEST</a>.


### -field UrbOSFeatureDescriptorRequest

Defines the format for a command to request a Microsoft OS Descriptor. For more information, see <a href="..\usb\ns-usb-_urb_os_feature_descriptor_request.md">_URB_OS_FEATURE_DESCRIPTOR_REQUEST</a>.


### -field UrbOpenStaticStreams

Defines the format for a command to open streams in a bulk endpoint of a USB 3.0 device. For more information, see <a href="..\usb\ns-usb-_urb_open_static_streams.md">_URB_OPEN_STATIC_STREAMS</a> and <a href="buses.how_to_open_streams_in_a_usb_endpoint">How to Open and Close Static Streams in a USB Bulk Endpoint</a>.


### -field UrbGetIsochPipeTransferPathDelays

Defines the format for a command to retrieve delays associated with isochronous transfer programming in the host controller and transfer completion so that the client driver can ensure that the device gets the isochronous packets in time. 
For more information, see <a href="..\usb\ns-usb-_urb_get_isoch_pipe_transfer_path_delays.md">_URB_GET_ISOCH_PIPE_TRANSFER_PATH_DELAYS</a>.


## -remarks
For information about the function codes to set in each structure, see <a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a>.


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
<a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_submit_urb.md">IOCTL_INTERNAL_USB_SUBMIT_URB</a>
</dt>
<dt>
<a href="buses.usb_structures_and_enumerations">USB Structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20URB structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

