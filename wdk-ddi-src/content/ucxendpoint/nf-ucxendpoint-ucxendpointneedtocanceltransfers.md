---
UID: NF:ucxendpoint.UcxEndpointNeedToCancelTransfers
title: UcxEndpointNeedToCancelTransfers function
author: windows-driver-content
description: The client driver calls this method before it cancels transfers on the wire.
old-location: buses\_ucxendpointneedtocanceltransfers.htm
old-project: usbref
ms.assetid: 4DA3FB63-D2D3-43E1-9420-29303176B837
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: ucxendpoint/UcxEndpointNeedToCancelTransfers, UcxEndpointNeedToCancelTransfers, UcxEndpointNeedToCancelTransfers method [Buses], buses._ucxendpointneedtocanceltransfers
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ucxendpoint.h
apiname:
-	UcxEndpointNeedToCancelTransfers
product: Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_CHARACTERISTIC_TYPE
req.product: Windows 10 or later.
---


# UcxEndpointNeedToCancelTransfers function
The client driver calls this method before it cancels transfers on the wire.

## Syntax

````
void UcxEndpointNeedToCancelTransfers(
  [in] UCXENDPOINT Endpoint
);
````

## Parameters

`Endpoint`

A handle to the endpoint object. The client driver retrieved the handle in a previous call to <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>.


## Return Value

This method does not return a value.

## Remarks

If needed, UCX coordinates with the hub driver to send a Clear TT buffer command to the TT Hub.

    After that operation completes, UCX invokes the client driver's  EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS callback function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ucxendpoint.h (include Ucxclass.h, Ucxendpoint.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcxEndpointNeedToCancelTransfers method%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>