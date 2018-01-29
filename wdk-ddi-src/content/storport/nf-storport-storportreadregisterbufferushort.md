---
UID : NF:storport.StorPortReadRegisterBufferUshort
title : StorPortReadRegisterBufferUshort function
author : windows-driver-content
description : The StorPortReadRegisterBufferUshort routine reads a value from a specified register address.
old-location : storage\storportreadregisterbufferushort.htm
old-project : storage
ms.assetid : 169f1089-ac17-4d4c-b989-018ff087aa39
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : StorPortReadRegisterBufferUshort, StorPortReadRegisterBufferUshort routine [Storage Devices], storprt_9ba740e5-78b0-464d-903c-6bb4c22788fd.xml, storage.storportreadregisterbufferushort, storport/StorPortReadRegisterBufferUshort
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : STOR_SPINLOCK
req.product : Windows 10 or later.
---


# StorPortReadRegisterBufferUshort function
The <b>StorPortReadRegisterBufferUshort</b> routine reads a value from a specified register address.

## Syntax

````
STORPORT_API VOID StorPortReadRegisterBufferUshort(
  _In_ PVOID   HwDeviceExtension,
  _In_ PUSHORT Register,
  _In_ PUSHORT Buffer,
  _In_ ULONG   Count
);
````

## Parameters

`HwDeviceExtension`

Pointer to the hardware device extension.

`Register`

Pointer to the register where the data is to be read.

`Buffer`

Pointer to the buffer that receives the data that is read.

`Count`

Number of data items to be read. Each data item has a size of <b>sizeof</b>(USHORT).


## Return Value

None

## Remarks

For more information, see <a href="..\srb\nf-srb-scsiportreadregisterbufferushort.md">ScsiPortReadRegisterBufferUshort</a>. For a nonbuffered version of this routine, see <a href="..\storport\nf-storport-storportreadregisterushort.md">StorPortReadRegisterUshort</a>.

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

<a href="..\srb\nf-srb-scsiportreadregisterbufferushort.md">ScsiPortReadRegisterBufferUshort</a>

<a href="..\storport\nf-storport-storportreadregisterushort.md">StorPortReadRegisterUshort</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReadRegisterBufferUshort routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>