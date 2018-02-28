---
UID: NF:ufxclient.UfxEndpointGetCommandQueue
title: UfxEndpointGetCommandQueue function
author: windows-driver-content
description: Returns the command queue previously created by UfxEndpointCreate.
old-location: buses\ufxendpointgetcommandqueue.htm
old-project: usbref
ms.assetid: BF84F0E4-3B0D-45B8-AC06-F6F761A37234
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UfxEndpointGetCommandQueue, UfxEndpointGetCommandQueue method [Buses], buses.ufxendpointgetcommandqueue, ufxclient/UfxEndpointGetCommandQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ufxclient.h
api_name:
-	UfxEndpointGetCommandQueue
product: Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---


# UfxEndpointGetCommandQueue function
Returns the command queue previously created by <a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a>.

## Syntax

````
WDFQUEUE UfxEndpointGetCommandQueue(
  [in] UFXENDPOINT UfxEndpoint
);
````

## Parameters

`UfxEndpoint`

A handle to an endpoint object returned from a previous call to <a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a>.


## Return Value

A handle to a framework queue object.

## Remarks

For an code example that shows how to create an endpoint object and initialize its context, see the Remarks section of <a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10  |
| **Target Platform** | Windows |
| **Header** | ufxclient.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | DISPATCH_LEVEL |

## See Also

<a href="..\ufxclient\nf-ufxclient-ufxendpointcreate.md">UfxEndpointCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UfxEndpointGetCommandQueue method%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>