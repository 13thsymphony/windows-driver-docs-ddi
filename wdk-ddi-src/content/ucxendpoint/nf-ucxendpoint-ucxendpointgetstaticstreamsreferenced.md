---
UID: NF:ucxendpoint.UcxEndpointGetStaticStreamsReferenced
title: UcxEndpointGetStaticStreamsReferenced function
author: windows-driver-content
description: Returns a referenced static streams object for the specified endpoint.
old-location: buses\_ucxendpointgetstaticstreamsreferenced.htm
old-project: usbref
ms.assetid: A9AB43A9-1409-4AA4-99DE-66D558F2303C
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UcxEndpointGetStaticStreamsReferenced, UcxEndpointGetStaticStreamsReferenced method [Buses], buses._ucxendpointgetstaticstreamsreferenced, ucxendpoint/UcxEndpointGetStaticStreamsReferenced
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
-	UcxEndpointGetStaticStreamsReferenced
product:
- Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_CHARACTERISTIC_TYPE
req.product: Windows 10 or later.
---


# UcxEndpointGetStaticStreamsReferenced function
Returns a referenced static streams object for the specified endpoint.

## Syntax

```
UCXSSTREAMS UcxEndpointGetStaticStreamsReferenced(
  UCXENDPOINT Endpoint,
  PVOID       Tag
);
```

## Parameters

`Endpoint`

A handle to the endpoint object for which the static streams object is requested. The client driver retrieved the handle in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>.

`Tag`

A driver-defined value that the framework stores as an identification tag for the object reference.


## Return Value

A handle to the stream object if it is opened with the endpoint. Otherwise, NULL.

## Remarks

The client driver can use this function to determine whether it has created a streams object for this endpoint. If it create the object the method returns the  UCXSSTREAMS handle. The method returns NULL if the object was not created, or if the client driver failed the framework request object passed in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187832">EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE</a> callback. Any call to this method must be matched by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548746">WdfObjectDereferenceWithTag</a> by using the same Tag.

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