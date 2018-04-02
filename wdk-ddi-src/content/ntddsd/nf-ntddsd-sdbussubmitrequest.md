---
UID: NF:ntddsd.SdBusSubmitRequest
title: SdBusSubmitRequest function
author: windows-driver-content
description: The SdBusSubmitRequest routine sends a synchronous Secure Digital (SD) request to the bus driver.
old-location: sd\sdbussubmitrequest.htm
old-project: SD
ms.assetid: 8f794681-afa9-474b-a3b9-bc7c21c7c423
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SD.sdbussubmitrequest, SdBusSubmitRequest, SdBusSubmitRequest function [Buses], ntddsd/SdBusSubmitRequest, sd-rtns_2709a5bb-0cc9-42b0-9fd1-2b8206a383d5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddsd.h
req.include-header: Ntddsd.h
req.target-type: Desktop
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
req.irql: "<DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddsd.h
api_name:
-	SdBusSubmitRequest
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---


# SdBusSubmitRequest function
The <b>SdBusSubmitRequest</b> routine sends a synchronous Secure Digital (SD) request to the bus driver.

## Syntax

```
NTSTATUS SdBusSubmitRequest(
  PVOID                 InterfaceContext,
  PSDBUS_REQUEST_PACKET Packet
);
```

## Parameters

`InterfaceContext`

Contains the context information returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537906">SdBusOpenInterface</a> routine in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/92b8762d-8af3-493c-aa1d-bc245b0cbd83">SDBUS_INTERFACE_STANDARD</a> structure.

`Packet`

TBD


## Return Value

Returns STATUS_SUCCESS if the operation succeeds, or the appropriate error code if the operation fails.

## Remarks

The <b>SdBusSubmitRequest</b> routine completes the request synchronously. It never returns a status code of STATUS_PENDING, but waits for the request to completed before returning.

This routine is a wrapper for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537914">SdBusSubmitRequestAsync</a> routine. 

Callers of <a href="https://msdn.microsoft.com/library/windows/hardware/ff537914">SdBusSubmitRequestAsync</a> must be running at IRQL &lt;= DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntddsd.h (include Ntddsd.h) |
| **IRQL** | "<DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/92b8762d-8af3-493c-aa1d-bc245b0cbd83">SDBUS_INTERFACE_STANDARD</a>



<a href="https://msdn.microsoft.com/09b30bf0-fe85-4ad5-bd3e-113ed3a093ac">SDBUS_REQUEST_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537906">SdBusOpenInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537914">SdBusSubmitRequestAsync</a>