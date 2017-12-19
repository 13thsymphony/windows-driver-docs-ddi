---
UID: NS.USB._URB_PIPE_REQUEST
title: _URB_PIPE_REQUEST
author: windows-driver-content
description: The _URB_PIPE_REQUEST structure is used by USB client drivers to clear a stall condition on an endpoint.
old-location: buses\_urb_pipe_request.htm
old-project: UsbRef
ms.assetid: 611bddf9-befd-4d2f-8e7d-7b5fe0744c03
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _URB_PIPE_REQUEST,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usb.h
req.include-header: Usb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: _URB_PIPE_REQUEST
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

# _URB_PIPE_REQUEST structure



## -description
The <b>_URB_PIPE_REQUEST</b> structure is used by USB client drivers to clear a stall condition on an endpoint.



## -syntax

````
struct _URB_PIPE_REQUEST {
  struct URB_HEADER  Hdr;
  USBD_PIPE_HANDLE  PipeHandle;
  ULONG             Reserved;
};
````


## -struct-fields

### -field Hdr

Pointer to the <a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be one of the following: 

<ul>
<li>URB_FUNCTION_SYNC_RESET_PIPE_AND_CLEAR_STALL</li>
<li>URB_FUNCTION_SYNC_RESET_PIPE</li>
<li>URB_FUNCTION_SYNC_CLEAR_STALL</li>
<li>URB_FUNCTION_ABORT_PIPE</li>
<li>URB_FUNCTION_CLOSE_STATIC_STREAMS</li>
</ul>
 The <b>Hdr.Length</b> member must be <code>sizeof(_URB_PIPE_REQUEST)</code>.


### -field PipeHandle

Specifies an opaque handle to the bulk or interrupt pipe. The host controller driver returns this handle when the client driver selects the device configuration with a URB of type URB_FUNCTION_SELECT_CONFIGURATION or when the client driver changes the settings for an interface with a URB of type URB_FUNCTION_SELECT_INTERFACE.


### -field Reserved

Reserved. Do not use.


## -remarks
The reserved members of this structure must be treated as opaque and are reserved for system use.


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
<a href="buses.urb">URB</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a>
</dt>
<dt>
<a href="buses.usb_structures_and_enumerations">USB Structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20_URB_PIPE_REQUEST structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

