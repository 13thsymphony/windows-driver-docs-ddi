---
UID : NI:usbscan.IOCTL_GET_USB_DESCRIPTOR
title : IOCTL_GET_USB_DESCRIPTOR
author : windows-driver-content
description : Returns a specified USB Descriptor.
old-location : image\ioctl_get_usb_descriptor.htm
old-project : image
ms.assetid : a5490a2a-d406-4029-b8be-446236a936bb
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : image.ioctl_get_usb_descriptor, IOCTL_GET_USB_DESCRIPTOR control code [Imaging Devices], IOCTL_GET_USB_DESCRIPTOR, usbscan/IOCTL_GET_USB_DESCRIPTOR, stifnc_9d8ca100-d268-4e51-88fb-925e0a029ece.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : usbscan.h
req.include-header : Usbscan.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : RAW_PIPE_TYPE
req.product : Windows 10 or later.
---

# IOCTL_GET_USB_DESCRIPTOR IOCTL
Returns a specified USB Descriptor.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
Pointer to a <a href="..\usbscan\ns-usbscan-_usbscan_get_descriptor.md">USBSCAN_GET_DESCRIPTOR</a> structure.

### Input Buffer Length
Size of the input buffer.

### Output Buffer
Pointer to a <a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a>, <a href="..\usbspec\ns-usbspec-_usb_string_descriptor.md">USB_STRING_DESCRIPTOR</a>, or <a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a> structure.

### Output Buffer Length
Size of the output buffer.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.

## Remarks
<h3><a id="ddk_ioctl_get_usb_descriptor_si"></a><a id="DDK_IOCTL_GET_USB_DESCRIPTOR_SI"></a>DeviceIoControl Parameters</h3>

When the <b>DeviceloControl</b> function is called with the IOCTL_GET_USB_DESCRIPTOR I/O control code, the caller must specify the address of a <a href="..\usbscan\ns-usbscan-_usbscan_get_descriptor.md">USBSCAN_GET_DESCRIPTOR</a> structure as the function's <i>lpInBuffer</i> parameter. Depending on the value specified for the <b>DescriptorType</b> member of the USBSCAN_GET_DESCRIPTOR structure, the function's <i>lpOutbuffer</i> parameter must point to either a <a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a>, <a href="..\usbspec\ns-usbspec-_usb_string_descriptor.md">USB_STRING_DESCRIPTOR</a>, or <a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a> structure.

The kernel-mode driver obtains a USB descriptor by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff538943">UsbBuildGetDescriptorRequest</a>.

For more information, see <a href="https://msdn.microsoft.com/f9216d3c-4930-4c26-8eac-6ee500b038e0">Accessing Kernel-Mode Drivers for Still Image Devices</a>.

For more information about USB descriptors, see the <i>Universal Serial Bus Specification</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | usbscan.h (include Usbscan.h) |
| **IRQL** |  |