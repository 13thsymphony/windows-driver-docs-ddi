---
UID: NE.usb._USBD_PIPE_TYPE
title: _USBD_PIPE_TYPE
author: windows-driver-content
description: The USBD_PIPE_TYPE enumerator indicates the type of pipe.
old-location: buses\usbd_pipe_type.htm
old-project: usbref
ms.assetid: 4522a7d0-d297-4668-bb4e-e4ceae18f52a
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _USBD_PIPE_TYPE, USBD_PIPE_TYPE
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
req.alt-api: USBD_PIPE_TYPE
req.alt-loc: usb.h
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
req.product: Windows 10 or later.
---

# _USBD_PIPE_TYPE enumeration



## -description
The <b>USBD_PIPE_TYPE</b> enumerator indicates the type of pipe.


## -syntax

````
typedef enum _USBD_PIPE_TYPE { 
  UsbdPipeTypeControl      = 0,
  UsbdPipeTypeIsochronous  = 1,
  UsbdPipeTypeBulk         = 2,
  UsbdPipeTypeInterrupt    = 3
} USBD_PIPE_TYPE;
````


## -enum-fields

### -field UsbdPipeTypeControl

Indicates that the pipe is a control pipe. 

### -field UsbdPipeTypeIsochronous

Indicates that the pipe is an isochronous transfer pipe.

### -field UsbdPipeTypeBulk

Indicates that the pipe is a bulk transfer pipe. 

### -field UsbdPipeTypeInterrupt

Indicates that the pipe is a interrupt pipe. 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Usb.h (include Usb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.usb_enumerations">USB Constants and Enumerations</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_PIPE_TYPE enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
