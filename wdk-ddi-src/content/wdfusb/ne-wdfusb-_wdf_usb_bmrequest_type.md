---
UID: NE:wdfusb._WDF_USB_BMREQUEST_TYPE
title: "_WDF_USB_BMREQUEST_TYPE"
author: windows-driver-content
description: The WDF_USB_BMREQUEST_TYPE enumeration identifies the data transfer type for a USB control transfer.
old-location: wdf\wdf_usb_bmrequest_type.htm
old-project: wdf
ms.assetid: c20e7aec-32e7-401d-8c40-aa6ac191e857
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: BmRequestClass, BmRequestStandard, BmRequestVendor, DFUsbRef_01dc6407-8fa2-462a-848c-2a8fc53ef50b.xml, WDF_USB_BMREQUEST_TYPE, WDF_USB_BMREQUEST_TYPE enumeration, _WDF_USB_BMREQUEST_TYPE, kmdf.wdf_usb_bmrequest_type, wdf.wdf_usb_bmrequest_type, wdfusb/BmRequestClass, wdfusb/BmRequestStandard, wdfusb/BmRequestVendor, wdfusb/WDF_USB_BMREQUEST_TYPE
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
-	WDF_USB_BMREQUEST_TYPE
product: Windows
targetos: Windows
req.typenames: WDF_USB_BMREQUEST_TYPE
req.product: Windows 10 or later.
---

# _WDF_USB_BMREQUEST_TYPE Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_BMREQUEST_TYPE</b> enumeration identifies the data transfer type for a USB control transfer.

## Syntax
````
typedef enum _WDF_USB_BMREQUEST_TYPE { 
  BmRequestStandard  = BMREQUEST_STANDARD,
  BmRequestClass     = BMREQUEST_CLASS,
  BmRequestVendor    = BMREQUEST_VENDOR
} WDF_USB_BMREQUEST_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>BmRequestStandard</td>
                    <td>The data transfer is a standard USB control transfer.</td>
                </tr>
            
                <tr>
                    <td>BmRequestClass</td>
                    <td>The data transfer is a device class-specific USB control transfer.</td>
                </tr>
            
                <tr>
                    <td>BmRequestVendor</td>
                    <td>The data transfer is a vendor-specific USB control transfer.</td>
                </tr>
</table>

## Remarks

The <b>WDF_USB_BMREQUEST_TYPE</b> enumeration is used in the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure.

For more information about data transfer types for a USB control transfer, see the USB specification.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfusb.h (include Wdfusb.h) |

## See Also

<a href="..\wdfusb\ns-wdfusb-_wdf_usb_control_setup_packet.md">WDF_USB_CONTROL_SETUP_PACKET</a>