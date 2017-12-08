---
UID: NC.ucxendpoint.EVT_UCX_ENDPOINT_PURGE
title: EVT_UCX_ENDPOINT_PURGE
author: windows-driver-content
description: The client driver's implementation that completes all outstanding I/O requests on the endpoint.
old-location: buses\evt_ucx_endpoint_purge.htm
old-project: usbref
ms.assetid: e4ceb597-ebfe-4016-ba83-e5246a70f566
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS, UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: PEVT_UCX_ENDPOINT_PURGE
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
req.irql: DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# EVT_UCX_ENDPOINT_PURGE callback



## -description
The client driver's implementation that completes all outstanding I/O requests on the endpoint.


## -prototype

````
EVT_UCX_ENDPOINT_PURGE EvtUcxEndpointPurge;

VOID EvtUcxEndpointPurge(
  _In_ UCXCONTROLLER UcxController,
  _In_ UCXENDPOINT   Endpoint
)
{ ... }

typedef EVT_UCX_ENDPOINT_PURGE PEVT_UCX_ENDPOINT_PURGE;
````


## -parameters

### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="buses._ucxcontrollercreate">UcxControllerCreate</a> method.

### -param Endpoint [in]

A handle to a UCXENDPOINT object that represents the endpoint.

## -returns
This callback function does not return a value.

## -remarks
The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="buses._ucxendpointcreate">UcxEndpointCreate</a>
 method.

Typically, this function calls <a href="wdf.wdfioqueuepurge">WdfIoQueuePurge</a>.

After UCX calls this function, the client driver fails subsequent I/O requests until UCX calls the client driver's <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_start.md">EVT_UCX_ENDPOINT_START</a> callback function.

## -requirements
<table>
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
DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfioqueuepurge">WdfIoQueuePurge</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_ENDPOINT_PURGE callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
