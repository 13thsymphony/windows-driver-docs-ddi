---
UID : NE:wdfusb._WDF_USB_BMREQUEST_DIRECTION
title : "_WDF_USB_BMREQUEST_DIRECTION"
author : windows-driver-content
description : The WDF_USB_BMREQUEST_DIRECTION enumeration identifies the data transfer direction for a USB control transfer.
old-location : wdf\wdf_usb_bmrequest_direction.htm
old-project : wdf
ms.assetid : e39748b8-d84c-4f9e-a790-bff192a6769c
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : BmRequestDeviceToHost, wdfusb/BmRequestDeviceToHost, DFUsbRef_c758891d-14e3-4034-8e95-b896470437fd.xml, _WDF_USB_BMREQUEST_DIRECTION, wdf.wdf_usb_bmrequest_direction, WDF_USB_BMREQUEST_DIRECTION, wdfusb/BmRequestHostToDevice, WDF_USB_BMREQUEST_DIRECTION enumeration, kmdf.wdf_usb_bmrequest_direction, wdfusb/WDF_USB_BMREQUEST_DIRECTION, BmRequestHostToDevice
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wdfusb.h
req.include-header : Wdfusb.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<=DISPATCH_LEVEL  (See Remarks section.)"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_USB_BMREQUEST_DIRECTION
req.product : Windows 10 or later.
---

# _WDF_USB_BMREQUEST_DIRECTION Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_BMREQUEST_DIRECTION</b> enumeration identifies the data transfer direction for a USB control transfer.

## Syntax
````
typedef enum _WDF_USB_BMREQUEST_DIRECTION { 
  BmRequestHostToDevice  = BMREQUEST_HOST_TO_DEVICE,
  BmRequestDeviceToHost  = BMREQUEST_DEVICE_TO_HOST
} WDF_USB_BMREQUEST_DIRECTION;
````

## Constants

<table>

<tr>
<td>BmRequestDeviceToHost</td>
<td>The data transfer direction is from the device to the host system.</td>
</tr>

<tr>
<td>BmRequestHostToDevice</td>
<td>The data transfer direction is from the host system to the device.</td>
</tr>
</table>

## Remarks

The <b>WDF_USB_BMREQUEST_DIRECTION</b> enumeration is used in the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure.

For more information about the data transfer direction for a USB control transfer, see the USB specification.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |

## See Also

<a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_BMREQUEST_DIRECTION enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>