---
UID: NE:usb._USBD_PIPE_TYPE
title: "_USBD_PIPE_TYPE"
author: windows-driver-content
description: The USBD_PIPE_TYPE enumerator indicates the type of pipe.
old-location: buses\usbd_pipe_type.htm
old-project: usbref
ms.assetid: 4522a7d0-d297-4668-bb4e-e4ceae18f52a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: USBD_PIPE_TYPE, USBD_PIPE_TYPE enumeration [Buses], UsbdPipeTypeBulk, UsbdPipeTypeControl, UsbdPipeTypeInterrupt, UsbdPipeTypeIsochronous, _USBD_PIPE_TYPE, buses.usbd_pipe_type, usb/USBD_PIPE_TYPE, usb/UsbdPipeTypeBulk, usb/UsbdPipeTypeControl, usb/UsbdPipeTypeInterrupt, usb/UsbdPipeTypeIsochronous, usbstrct_a1fda372-f509-4667-a615-b68936b0a42b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: usb.h
req.include-header: Usb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usb.h
api_name:
-	USBD_PIPE_TYPE
product: Windows
targetos: Windows
req.typenames: USBD_PIPE_TYPE
req.product: Windows 10 or later.
---

# _USBD_PIPE_TYPE Enumeration
The <b>USBD_PIPE_TYPE</b> enumerator indicates the type of pipe.

## Syntax
````
typedef enum _USBD_PIPE_TYPE { 
  UsbdPipeTypeControl      = 0,
  UsbdPipeTypeIsochronous  = 1,
  UsbdPipeTypeBulk         = 2,
  UsbdPipeTypeInterrupt    = 3
} USBD_PIPE_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>UsbdPipeTypeControl</td>
                    <td>Indicates that the pipe is a control pipe.</td>
                </tr>
            
                <tr>
                    <td>UsbdPipeTypeIsochronous</td>
                    <td>Indicates that the pipe is an isochronous transfer pipe.</td>
                </tr>
            
                <tr>
                    <td>UsbdPipeTypeBulk</td>
                    <td>Indicates that the pipe is a bulk transfer pipe.</td>
                </tr>
            
                <tr>
                    <td>UsbdPipeTypeInterrupt</td>
                    <td>Indicates that the pipe is a interrupt pipe.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usb.h (include Usb.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539322">USB Constants and Enumerations</a>