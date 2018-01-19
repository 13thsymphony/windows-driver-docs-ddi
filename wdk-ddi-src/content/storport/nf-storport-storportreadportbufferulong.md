---
UID : NF:storport.StorPortReadPortBufferUlong
title : StorPortReadPortBufferUlong function
author : windows-driver-content
description : The StorPortReadPortBufferUlong routine reads a value from a specified port address.
old-location : storage\storportreadportbufferulong.htm
old-project : storage
ms.assetid : 0b7366db-e80f-41f0-9a51-d1c139e948d8
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : StorPortReadPortBufferUlong
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : storport.h
req.include-header : Storport.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : StorPortReadPortBufferUlong
req.alt-loc : Storport.lib,Storport.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Storport.lib
req.dll : 
req.irql : 
req.typenames : STOR_SPINLOCK
req.product : Windows 10 or later.
---


# StorPortReadPortBufferUlong function
The <b>StorPortReadPortBufferUlong</b> routine reads a value from a specified port address.

## Syntax

````
STORPORT_API VOID StorPortReadPortBufferUlong(
  _In_ PVOID  HwDeviceExtension,
  _In_ PULONG Port,
  _In_ PULONG Buffer,
  _In_ ULONG  Count
);
````

## Parameters

`HwDeviceExtension`

Pointer to the hardware device extension.

`Port`

Pointer to the address from which to read.

`Buffer`

Pointer to the buffer that receives the data that is read.

`Count`

Specifies the number of data items to be read. Each data item has a size of sizeof(ULONG).


## Return Value

None

## Remarks

For more information, see the <a href="..\srb\nf-srb-scsiportreadportbufferulong.md">ScsiPortReadPortBufferUlong</a> routine. For a nonbuffered version of this routine, see <a href="..\storport\nf-storport-storportreadportulong.md">StorPortReadPortUlong</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | storport.h (include Storport.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\srb\nf-srb-scsiportreadportbufferulong.md">ScsiPortReadPortBufferUlong</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportreadportulong.md">StorPortReadPortUlong</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReadPortBufferUlong routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>