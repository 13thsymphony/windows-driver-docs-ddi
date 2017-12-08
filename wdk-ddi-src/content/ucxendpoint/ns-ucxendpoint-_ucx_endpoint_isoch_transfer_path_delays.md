---
UID: NS.UCXENDPOINT._UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS
title: _UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS
author: windows-driver-content
description: Stores the isochronous transfer path delay values.
old-location: buses\ucx_endpoint_isoch_transfer_path_delays.htm
old-project: usbref
ms.assetid: 5001C27B-EA5F-43C4-AD59-84B42041262E
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS, *PUCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS, UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxendpoint.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS
req.alt-loc: Ucxendpoint.h
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

# _UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS structure



## -description
Stores the isochronous transfer path delay values. 


## -syntax

````
typedef struct _UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS {
  ULONG MaximumSendPathDelayInMilliSeconds;
  ULONG MaximumCompletionPathDelayInMilliSeconds;
} UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS, *PUCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS;
````


## -struct-fields

### -field MaximumSendPathDelayInMilliSeconds

The maximum delay in milliseconds from the time the  client driver's isochronous transfer is received by the USB driver stack to the time the transfer is programmed in the host controller. The host controller could either be a local host (as in case of wired USB) or it could be a remote controller as in case of Media-Agnostic USB (MA-USB). In case of MA-USB, it includes the maximum delay associated with the network medium.  
  

### -field MaximumCompletionPathDelayInMilliSeconds

The maximum delay in milliseconds from the time an isochronous transfer is completed by the (local or remote) host controller to the time the corresponding client driver's request is completed by the USB driver stack. For MA-USB, it includes the maximum delay associated with the network medium.

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
<dt>Ucxendpoint.h (include Ucxclass.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_get_isoch_transfer_path_delays.md">EVT_UCX_ENDPOINT_GET_ISOCH_TRANSFER_PATH_DELAYS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
