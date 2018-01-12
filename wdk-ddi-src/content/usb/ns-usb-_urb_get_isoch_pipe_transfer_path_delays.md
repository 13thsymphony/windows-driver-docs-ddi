---
UID: NS:usb._URB_GET_ISOCH_PIPE_TRANSFER_PATH_DELAYS
title: _URB_GET_ISOCH_PIPE_TRANSFER_PATH_DELAYS
author: windows-driver-content
description: The _URB_GET_ISOCH_PIPE_TRANSFER_PATH_DELAYS structure is used by USB client drivers to retrieve delays associated with isochronous transfer programming in the host controller and transfer completion so that the client driver can ensure that the device gets the isochronous packets in time.
old-location: buses\_urb_get_isoch_pipe_transfer_path_delays.htm
old-project: usbref
ms.assetid: 70B74088-C537-4104-A535-F41A24BB72A5
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _URB_GET_ISOCH_PIPE_TRANSFER_PATH_DELAYS,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usb.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: _URB_GET_ISOCH_PIPE_TRANSFER_PATH_DELAYS
req.alt-loc: Usb.h
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
req.typenames: 
req.product: Windows 10 or later.
---

# _URB_GET_ISOCH_PIPE_TRANSFER_PATH_DELAYS structure



## -description
The <b>_URB_GET_ISOCH_PIPE_TRANSFER_PATH_DELAYS</b> structure is used by USB client drivers to retrieve delays associated with isochronous transfer programming in the host controller and transfer completion so that the client driver can ensure that the device gets the isochronous packets in time. 




## -syntax

````
struct _URB_GET_ISOCH_PIPE_TRANSFER_PATH_DELAYS {
  struct URB_HEADER  Hdr;
  USBD_PIPE_HANDLE  PipeHandle;
  ULONG             MaximumSendPathDelayInMilliSeconds;
  ULONG             MaximumCompletionPathDelayInMilliSeconds;
};
````


## -struct-fields

### -field Hdr

Pointer to a <a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be URB_FUNCTION_GET_ISOCH_PIPE_TRANSFER_PATH_DELAYS, and <b>Hdr.Length</b> must be set to <code>sizeofsizeof(_URB_GET_ISOCH_PIPE_TRANSFER_PATH_DELAYS)</code>.


### -field PipeHandle

Specifies an opaque handle to pipe associated with the endpoint. The host controller driver returns this handle when the client driver selects the device configuration with a URB of type URB_FUNCTION_SELECT_CONFIGURATION or when the client driver changes the settings for an interface with a URB of type URB_FUNCTION_SELECT_INTERFACE.  


### -field MaximumSendPathDelayInMilliSeconds

Returns the maximum delay in milliseconds from the time the  client driver's isochronous transfer is received by the USB driver stack to the time the transfer is programmed in the host controller. The host controller could either be a local host (as in case of wired USB) or it could be a remote controller as in case of Media-Agnostic USB (MA-USB). In case of MA-USB, it includes the maximum delay associated with the network medium.  
  


### -field MaximumCompletionPathDelayInMilliSeconds

Returns the maximum delay in milliseconds from the time an isochronous transfer is completed by the (local or remote) host controller to the time the corresponding client driver's request is completed by the USB driver stack. For MA-USB, it includes the maximum delay associated with the network medium.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10, version 1709

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usb.h</dt>
</dl>
</td>
</tr>
</table>