---
UID: NF:storport.StorPortReadPortUchar
title: StorPortReadPortUchar function
author: windows-driver-content
description: The StorPortReadPortUchar routine reads a value from a specified port address
old-location: storage\storportreadportuchar.htm
old-project: storage
ms.assetid: 6898ca45-e4a2-41ad-a47e-6dfbcc60b00a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortReadPortUchar routine [Storage Devices], StorPortReadPortUchar, storprt_de88c383-95ac-4f3e-b02d-aec76132e4c3.xml, storport/StorPortReadPortUchar, storage.storportreadportuchar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Storport.lib
-	Storport.dll
apiname:
-	StorPortReadPortUchar
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortReadPortUchar function
The <b>StorPortReadPortUchar</b> routine reads a value from a specified port address

## Syntax

````
STORPORT_API UCHAR StorPortReadPortUchar(
  _In_ PVOID  HwDeviceExtension,
  _In_ PUCHAR Port
);
````

## Parameters

`HwDeviceExtension`

Pointer to the hardware device extension.

`Port`

Pointer to the address from which to read.


## Return Value

<b>StorPortReadPortUchar</b> returns an unsigned character of data.

## Remarks

For more information, see the <a href="..\srb\nf-srb-scsiportreadportbufferuchar.md">ScsiPortReadPortBufferUchar</a> routine. For a buffered version of this routine, see <a href="..\storport\nf-storport-storportreadportbufferuchar.md">StorPortReadPortBufferUchar</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |

## See Also

<a href="..\storport\nf-storport-storportreadportbufferuchar.md">StorPortReadPortBufferUchar</a>

<a href="..\srb\nf-srb-scsiportreadportbufferuchar.md">ScsiPortReadPortBufferUchar</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReadPortUchar routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>