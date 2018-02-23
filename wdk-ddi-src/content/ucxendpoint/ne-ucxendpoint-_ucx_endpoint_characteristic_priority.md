---
UID: NE:ucxendpoint._UCX_ENDPOINT_CHARACTERISTIC_PRIORITY
title: "_UCX_ENDPOINT_CHARACTERISTIC_PRIORITY"
author: windows-driver-content
description: Indicates the priority of endpoints.
old-location: buses\ucx_endpoint_characteristic_priority.htm
old-project: UsbRef
ms.assetid: 43031BE8-B94A-4B22-B9E2-CBF59A31F3A2
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_NONE, UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VOICE, _UCX_ENDPOINT_CHARACTERISTIC_PRIORITY, buses.ucx_endpoint_characteristic_priority, ucxendpoint/UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY, UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY enumeration [Buses], ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VOICE, ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_INTERACTIVE, UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VIDEO, ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VIDEO, UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY, UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_NONE, UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_INTERACTIVE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucxendpoint.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ucxendpoint.h
apiname:
-	UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY
req.product: Windows 10 or later.
---

# _UCX_ENDPOINT_CHARACTERISTIC_PRIORITY Enumeration
Indicates the priority of endpoints.

## Syntax
````
typedef enum _UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY { 
  UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_NONE              = 0x00,
  UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VIDEO        = 0x01,
  UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VOICE        = 0x02,
  UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_INTERACTIVE  = 0x03
} UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY ;
````

## Constants

<table>
            
                <tr>
                    <td>UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_INTERACTIVE</td>
                    <td>Bulk endpoint with interactive has the priority.</td>
                </tr>
            
                <tr>
                    <td>UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VIDEO</td>
                    <td>Bulk endpoint with video has the priority.</td>
                </tr>
            
                <tr>
                    <td>UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VOICE</td>
                    <td>Bulk endpoint with voice has the priority.</td>
                </tr>
            
                <tr>
                    <td>UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_NONE</td>
                    <td>No characteristics of the endpoint.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows 10, version 1709 |
| **Header** | ucxendpoint.h (include Ucxclass.h) |

## See Also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/usbcon/usb-client-drivers-for-ma-usb">USB client drivers for Media-Agnostic (MA-USB)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY enumeration%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>