---
UID : NS:usbspec._USB_ENDPOINT_DESCRIPTOR
title : "_USB_ENDPOINT_DESCRIPTOR"
author : windows-driver-content
description : The USB_ENDPOINT_DESCRIPTOR structure is used by USB client drivers to retrieve a USB-defined endpoint descriptor.
old-location : buses\usb_endpoint_descriptor.htm
old-project : usbref
ms.assetid : fb4f25e4-cf72-4308-9685-edc62b1cc510
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : usbspec/PUSB_ENDPOINT_DESCRIPTOR, usbstrct_3e135b0b-f2a1-4d7a-92b8-4a9e2724726c.xml, PUSB_ENDPOINT_DESCRIPTOR, USB_ENDPOINT_DESCRIPTOR, *PUSB_ENDPOINT_DESCRIPTOR, buses.usb_endpoint_descriptor, usbspec/USB_ENDPOINT_DESCRIPTOR, _USB_ENDPOINT_DESCRIPTOR, USB_ENDPOINT_DESCRIPTOR structure [Buses], PUSB_ENDPOINT_DESCRIPTOR structure pointer [Buses]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : usbspec.h
req.include-header : Usb100.h
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
req.typenames : "*PUSB_ENDPOINT_DESCRIPTOR, USB_ENDPOINT_DESCRIPTOR"
req.product : Windows 10 or later.
---

# _USB_ENDPOINT_DESCRIPTOR structure
The <b>USB_ENDPOINT_DESCRIPTOR</b> structure is used by USB client drivers to retrieve a USB-defined endpoint descriptor.

## Syntax
````
typedef struct _USB_ENDPOINT_DESCRIPTOR {
  UCHAR  bLength;
  UCHAR  bDescriptorType;
  UCHAR  bEndpointAddress;
  UCHAR  bmAttributes;
  USHORT wMaxPacketSize;
  UCHAR  bInterval;
} USB_ENDPOINT_DESCRIPTOR, *PUSB_ENDPOINT_DESCRIPTOR;
````

## Members


`bDescriptorType`

Specifies the descriptor type. Must be set to USB_ENDPOINT_DESCRIPTOR_TYPE.

`bEndpointAddress`

Specifies the USB-defined endpoint address. The four low-order bits specify the endpoint number. The high-order bit specifies the direction of data flow on this endpoint: 1 for in, 0 for out.

`bInterval`

The  <b>bInterval</b> value contains the polling interval for interrupt and isochronous endpoints. For other types of endpoint, this value should be ignored. This value reflects the device's configuration in firmware. Drivers cannot change it.

The polling interval, together with the speed of the device and the type of host controller, determine the frequency with which the driver should initiate an interrupt or an isochronous transfer. The value in <b>bInterval</b> does not represent a fixed amount of time. It is a relative value, and the actual polling frequency will also depend on whether the device and the USB host controller operate at low, full or high speed. 

If either the host controller or the device operates at low speed, the period of time between interrupt transfers (also known as the polling "period") is measured in units of 1 millisecond frames, and the period is related to the value in <b>bInterval</b> as indicated the following table:
<table>
<tr>
<th>Value of bInterval</th>
<th>Polling Period (1-millisecond frames)</th>
<th>Interrupt</th>
</tr>
<tr>
<td>0 to 15</td>
<td>8</td>
<td>Supported.</td>
</tr>
<tr>
<td>16 to 35</td>
<td>16</td>
<td>Supported.</td>
</tr>
<tr>
<td>36 to 255</td>
<td>32</td>
<td>Supported.</td>
</tr>
<tr>
<td>&gt; 255</td>
<td>Polling intervals &gt; 255 are forbidden by the USB specification.</td>
<td></td>
</tr>
</table> 

For devices and host controllers that can operate at full speed, the period is measured in units of 1 millisecond frames, and the period is related to the value in <b>bInterval</b> as indicated the following table:
<table>
<tr>
<th>Value of bInterval</th>
<th>Polling Period (1-millisecond frames)</th>
<th>Interrupt  </th>
<th>Isochronous</th>
</tr>
<tr>
<td>1</td>
<td>1</td>
<td>Supported.</td>
<td>Supported.</td>
</tr>
<tr>
<td>2 to 3</td>
<td>2</td>
<td>Supported.</td>
<td>Supported.</td>
</tr>
<tr>
<td>4 to 7</td>
<td>4</td>
<td>Supported.</td>
<td>Supported.</td>
</tr>
<tr>
<td>8 to 15</td>
<td>8</td>
<td>Supported.</td>
<td>Supported.</td>
</tr>
<tr>
<td>16 to 31</td>
<td>16</td>
<td>Supported.</td>
<td>Not supported.</td>
</tr>
<tr>
<td>32 to 255</td>
<td>32</td>
<td>Supported.</td>
<td>Not supported.</td>
</tr>
<tr>
<td>&gt; 255</td>
<td>Polling intervals &gt; 255 are forbidden by the USB specification.</td>
<td></td>
<td></td>
</tr>
</table> 

For devices and host controllers that can operate at high speed, the period is measured in units of microframes. There are eight microframes in each 1 millisecond frame. The period is related to the value in <b>bInterval</b> by the formula Period = 2 ** (<b>bInterval</b> - 1), as indicated the following table:
<table>
<tr>
<th>Value of bInterval</th>
<th>Polling Period (microframes)</th>
<th>Interrupt  </th>
<th>Isochronous</th>
</tr>
<tr>
<td>1</td>
<td>1</td>
<td>Supported.</td>
<td>Supported.</td>
</tr>
<tr>
<td>2</td>
<td>2</td>
<td>Supported.</td>
<td>Supported.</td>
</tr>
<tr>
<td>3</td>
<td>4</td>
<td>Supported.</td>
<td>Supported.</td>
</tr>
<tr>
<td>4</td>
<td>8</td>
<td>Supported.</td>
<td>Supported.</td>
</tr>
<tr>
<td>5</td>
<td>16</td>
<td>Supported.</td>
<td>Not supported.</td>
</tr>
<tr>
<td>6</td>
<td>32</td>
<td>Supported.</td>
<td>Not supported.</td>
</tr>
<tr>
<td>7 to 255</td>
<td>32</td>
<td>Supported.</td>
<td>Not supported.</td>
</tr>
<tr>
<td>&gt; 255</td>
<td>Polling intervals &gt; 255 are forbidden by the USB specification.</td>
<td></td>
<td></td>
</tr>
</table> 

The mappings in the preceding tables between periods and polling intervals are valid in Windows 2000 and later operating systems.

`bLength`

Specifies the length, in bytes, of this descriptor.

`bmAttributes`

The two low-order bits specify the endpoint type, one of USB_ENDPOINT_TYPE_CONTROL, USB_ENDPOINT_TYPE_ISOCHRONOUS, USB_ENDPOINT_TYPE_BULK, or USB_ENDPOINT_TYPE_INTERRUPT.

`wMaxPacketSize`

Specifies the maximum packet size that can be sent from or to this endpoint.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usbspec.h (include Usb100.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>

<a href="..\usb\ns-usb-_urb_control_descriptor_request.md">_URB_CONTROL_DESCRIPTOR_REQUEST</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538943">UsbBuildGetDescriptorRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_ENDPOINT_DESCRIPTOR structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>