---
UID: NF.ucxendpoint.UcxEndpointNeedToCancelTransfers
title: UcxEndpointNeedToCancelTransfers function
author: windows-driver-content
description: The client driver calls this method before it cancels transfers on the wire.
old-location: buses\_ucxendpointneedtocanceltransfers.htm
old-project: usbref
ms.assetid: 4DA3FB63-D2D3-43E1-9420-29303176B837
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: UcxEndpointNeedToCancelTransfers
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: UcxEndpointNeedToCancelTransfers
req.alt-loc: ucxendpoint.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# UcxEndpointNeedToCancelTransfers function



## -description
The client driver calls this method before it cancels transfers on the wire.



## -syntax

````
void UcxEndpointNeedToCancelTransfers(
  [in] UCXENDPOINT Endpoint
);
````


## -parameters

### -param Endpoint [in]

A handle to the endpoint object. The client driver retrieved the handle in a previous call to <a href="buses._ucxendpointcreate">UcxEndpointCreate</a>.


## -returns
This method does not return a value.


## -remarks
 If needed, UCX coordinates with the hub driver to send a Clear TT buffer command to the TT Hub.

    After that operation completes, UCX invokes the client driver's  EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS callback function.


## -requirements
<table>
<tr>
<th width="30%">
Minimum support

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ucxendpoint.h (include Ucxclass.h or Ucxendpoint.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses._ucxendpointcreate">UcxEndpointCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcxEndpointNeedToCancelTransfers method%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

