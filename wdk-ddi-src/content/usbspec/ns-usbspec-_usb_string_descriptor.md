---
UID : NS:usbspec._USB_STRING_DESCRIPTOR
title : _USB_STRING_DESCRIPTOR
author : windows-driver-content
description : The USB_STRING_DESCRIPTOR structure is used by USB client drivers to hold a USB-defined string descriptor.
old-location : buses\usb_string_descriptor.htm
old-project : usbref
ms.assetid : 20d76582-4138-4a45-940b-a8e9207946a5
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _USB_STRING_DESCRIPTOR, *PUSB_STRING_DESCRIPTOR, USB_STRING_DESCRIPTOR
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : usbspec.h
req.include-header : Usbioctl.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : USB_STRING_DESCRIPTOR
req.alt-loc : usbspec.h
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
req.typenames : "*PUSB_STRING_DESCRIPTOR, USB_STRING_DESCRIPTOR"
req.product : Windows 10 or later.
---

# _USB_STRING_DESCRIPTOR structure
The <b>USB_STRING_DESCRIPTOR</b> structure is used by USB client drivers to hold a USB-defined string descriptor.

## Syntax
````
typedef struct _USB_STRING_DESCRIPTOR {
  UCHAR bLength;
  UCHAR bDescriptorType;
  WCHAR bString[1];
} USB_STRING_DESCRIPTOR, *PUSB_STRING_DESCRIPTOR;
````

## Members

        
            `bDescriptorType`

            Specifies the descriptor type. Must always be USB_STRING_DESCRIPTOR_TYPE.
        
            `bLength`

            Specifies the length, in bytes, of the descriptor.
        
            `bString`

            Pointer to a client-allocated buffer that contains, on return from the host controller driver, a Unicode string with the requested string descriptor.

    ## Remarks
        This structure is used to hold a device, configuration, interface, class, vendor, endpoint, or device string descriptor. The string descriptor provides a human-readable description of the component.

Strings returned in <b>bString</b> are in Unicode format and the contents of the strings are device-defined.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usbspec.h (include Usbioctl.h) |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538943">UsbBuildGetDescriptorRequest</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_control_descriptor_request.md">_URB_CONTROL_DESCRIPTOR_REQUEST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_STRING_DESCRIPTOR structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>