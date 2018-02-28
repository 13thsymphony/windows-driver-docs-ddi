---
UID: NF:ntifs.IoSizeOfIrp
title: IoSizeOfIrp macro
author: windows-driver-content
description: The IoSizeOfIrp routine determines the size in bytes for an IRP, given the number of stack locations in the IRP.
old-location: kernel\iosizeofirp.htm
old-project: kernel
ms.assetid: b7a6f903-a986-464a-9c9c-12d44f9abf6a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IoSizeOfIrp, IoSizeOfIrp routine [Kernel-Mode Driver Architecture], k104_7c08c9ff-7731-462e-acb8-3793f85a84c2.xml, kernel.iosizeofirp, wdm/IoSizeOfIrp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: ntifs.h
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	IoSizeOfIrp
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoSizeOfIrp function
The <b>IoSizeOfIrp</b> routine determines the size in bytes for an IRP, given the number of stack locations in the IRP.

## Syntax

````
USHORT IoSizeOfIrp(
  _In_ CCHAR StackSize
);
````

## Parameters

`StackSize`

Specifies the number of stack locations for the IRP.


## Return Value

None

## Remarks

The input <i>StackSize</i> value is either that of the next-lower driver's device object or one more than that value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Desktop |
| **Header** | ntifs.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | ntifs.h |
| **IRQL** | Any level |

## See Also

<a href="..\ntddk\nf-ntddk-iomakeassociatedirp.md">IoMakeAssociatedIrp</a>



<a href="..\wdm\nf-wdm-ioallocateirp.md">IoAllocateIrp</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoSizeOfIrp routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>