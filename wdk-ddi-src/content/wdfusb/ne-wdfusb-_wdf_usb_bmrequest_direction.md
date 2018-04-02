---
UID: NE:wdfusb._WDF_USB_BMREQUEST_DIRECTION
title: "_WDF_USB_BMREQUEST_DIRECTION"
author: windows-driver-content
description: The WDF_USB_BMREQUEST_DIRECTION enumeration identifies the data transfer direction for a USB control transfer.
old-location: wdf\wdf_usb_bmrequest_direction.htm
old-project: wdf
ms.assetid: e39748b8-d84c-4f9e-a790-bff192a6769c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: BmRequestDeviceToHost, BmRequestHostToDevice, DFUsbRef_c758891d-14e3-4034-8e95-b896470437fd.xml, WDF_USB_BMREQUEST_DIRECTION, WDF_USB_BMREQUEST_DIRECTION enumeration, _WDF_USB_BMREQUEST_DIRECTION, kmdf.wdf_usb_bmrequest_direction, wdf.wdf_usb_bmrequest_direction, wdfusb/BmRequestDeviceToHost, wdfusb/BmRequestHostToDevice, wdfusb/WDF_USB_BMREQUEST_DIRECTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL  (See Remarks section.)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfusb.h
api_name:
-	WDF_USB_BMREQUEST_DIRECTION
product:
- Windows
targetos: Windows
req.typenames: WDF_USB_BMREQUEST_DIRECTION
req.product: Windows 10 or later.
---

# _WDF_USB_BMREQUEST_DIRECTION Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_BMREQUEST_DIRECTION</b> enumeration identifies the data transfer direction for a USB control transfer.

## Syntax
```
typedef enum _WDF_USB_BMREQUEST_DIRECTION {
  BmRequestHostToDevice  ,
  BmRequestDeviceToHost
} WDF_USB_BMREQUEST_DIRECTION;
```

## Constants

<table>
            
                <tr>
                    <td>BmRequestHostToDevice</td>
                    <td>The data transfer direction is from the host system to the device.</td>
                </tr>
            
                <tr>
                    <td>BmRequestDeviceToHost</td>
                    <td>The data transfer direction is from the device to the host system.</td>
                </tr>
</table>

## Remarks

The <b>WDF_USB_BMREQUEST_DIRECTION</b> enumeration is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure.

For more information about the data transfer direction for a USB control transfer, see the USB specification.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a>