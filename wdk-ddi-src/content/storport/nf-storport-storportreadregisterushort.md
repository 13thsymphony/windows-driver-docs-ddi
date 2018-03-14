---
UID: NF:storport.StorPortReadRegisterUshort
title: StorPortReadRegisterUshort macro
author: windows-driver-content
description: The StorPortReadRegisterUshort routine reads a value from a specified register address.
old-location: storage\storportreadregisterushort.htm
old-project: storage
ms.assetid: 11659e7d-db54-401c-a179-75cc5d411b55
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortReadRegisterUshort, StorPortReadRegisterUshort routine [Storage Devices], storage.storportreadregisterushort, storport/StorPortReadRegisterUshort, storprt_f477688d-54cb-4cb6-b713-0e70cfbf2139.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortReadRegisterUshort
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortReadRegisterUshort function
The <b>StorPortReadRegisterUshort</b> routine reads a value from a specified register address.

## Syntax

````
STORPORT_API USHORT StorPortReadRegisterUshort(
  _In_ PVOID   HwDeviceExtension,
  _In_ PUSHORT Register
);
````

## Parameters

`h`

TBD

`r`

TBD


## Return Value

None

## Remarks

For more information, see <a href="..\storport\nf-storport-scsiportreadregisterushort.md">ScsiPortReadRegisterUshort</a>. For a buffered version of this routine, see <a href="..\storport\nf-storport-storportreadregisterbufferushort.md">StorPortReadRegisterBufferUshort</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |

## See Also

<a href="..\storport\nf-storport-scsiportreadregisterushort.md">ScsiPortReadRegisterUshort</a>



<a href="..\storport\nf-storport-storportreadregisterbufferushort.md">StorPortReadRegisterBufferUshort</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReadRegisterUshort routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>