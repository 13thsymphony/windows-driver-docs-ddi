---
UID : NS:usbioctl._USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION
title : _USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION
author : windows-driver-content
description : The input buffer for the IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC request.
old-location : buses\usb_stop_tracking_for_time_sync_information.htm
old-project : usbref
ms.assetid : FFD7979B-48E9-433C-86A9-255F4F422BBA
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION, USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION, *PUSB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : usbioctl.h
req.include-header : TBD
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION
req.alt-loc : usbioctl.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <=DISPATCH_LEVEL
req.typenames : USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION, *PUSB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION
req.product : Windows 10 or later.
---

# _USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION structure
The input buffer for the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_stop_tracking_for_time_sync.md">IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC</a> request.

## Syntax
````
typedef struct _USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION {
  HANDLE TimeTrackingHandle;
} USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION, *PUSB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION;
````

## Members

        
            `TimeTrackingHandle`

            The time racking handle received in the previous <a href="..\usbioctl\ni-usbioctl-ioctl_usb_stop_tracking_for_time_sync.md">IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC</a> request.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usbioctl.h (include TBD) |

    ## See Also

        <dl>
<dt>
<a href="..\usbioctl\ni-usbioctl-ioctl_usb_stop_tracking_for_time_sync.md">IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>