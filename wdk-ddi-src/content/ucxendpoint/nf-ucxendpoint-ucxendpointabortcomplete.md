---
UID: NF:ucxendpoint.UcxEndpointAbortComplete
title: UcxEndpointAbortComplete function
author: windows-driver-content
description: Notifies UCX that a transfer abort operation has been completed on the specified endpoint object.
old-location: buses\_ucxendpointabortcomplete.htm
old-project: usbref
ms.assetid: 754BCC74-1EC2-429E-A711-E8958665A5A8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UcxEndpointAbortComplete, UcxEndpointAbortComplete method [Buses], buses._ucxendpointabortcomplete, ucxendpoint/UcxEndpointAbortComplete
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
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ucxendpoint.h
api_name:
-	UcxEndpointAbortComplete
product:
- Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_CHARACTERISTIC_TYPE
req.product: Windows 10 or later.
---


# UcxEndpointAbortComplete function
Notifies UCX that a transfer abort operation has been completed  on the specified endpoint object.

## Syntax

```
void UcxEndpointAbortComplete(
  UCXENDPOINT Endpoint
);
```

## Parameters

`Endpoint`

A handle to the endpoint object. The client driver retrieved the handle in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>.


## Return Value

This method does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10  |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ucxendpoint.h (include Ucxclass.h, Ucxendpoint.h) |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>