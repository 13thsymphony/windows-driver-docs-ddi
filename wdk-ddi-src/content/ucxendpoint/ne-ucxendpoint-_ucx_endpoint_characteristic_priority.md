---
UID: NE:ucxendpoint._UCX_ENDPOINT_CHARACTERISTIC_PRIORITY
title: "_UCX_ENDPOINT_CHARACTERISTIC_PRIORITY"
author: windows-driver-content
description: Indicates the priority of endpoints.
old-location: buses\ucx_endpoint_characteristic_priority.htm
old-project: usbref
ms.assetid: 43031BE8-B94A-4B22-B9E2-CBF59A31F3A2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY, UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY enumeration [Buses], UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_INTERACTIVE, UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VIDEO, UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VOICE, UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_NONE, _UCX_ENDPOINT_CHARACTERISTIC_PRIORITY, buses.ucx_endpoint_characteristic_priority, ucxendpoint/UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY, ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_INTERACTIVE, ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VIDEO, ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VOICE, ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_NONE
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ucxendpoint.h
api_name:
-	UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY
req.product: Windows 10 or later.
---

# _UCX_ENDPOINT_CHARACTERISTIC_PRIORITY Enumeration
Indicates the priority of endpoints.

## Syntax
```
typedef enum _UCX_ENDPOINT_CHARACTERISTIC_PRIORITY {
  UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_NONE              ,
  UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VIDEO        ,
  UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_VOICE        ,
  UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_INTERACTIVE
} UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY;
```

## Constants

<table>
            
                <tr>
                    <td>UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_NONE</td>
                    <td>No characteristics of the endpoint.</td>
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
                    <td>UCX_ENDPOINT_CHARACTERISTIC_PRIORITY_BULK_INTERACTIVE</td>
                    <td>Bulk endpoint with interactive has the priority.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows 10, version 1709 |
| **Header** | ucxendpoint.h (include Ucxclass.h) |

## See Also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/usbcon/usb-client-drivers-for-ma-usb">USB client drivers for Media-Agnostic (MA-USB)</a>