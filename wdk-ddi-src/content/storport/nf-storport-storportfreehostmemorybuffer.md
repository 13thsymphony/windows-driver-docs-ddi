---
UID : NF:storport.StorPortFreeHostMemoryBuffer
title : StorPortFreeHostMemoryBuffer function
author : windows-driver-content
description : The StorPortFreeHostMemoryBuffer routine frees the physically contiguous memory that was allocated to be used for a Host Memory Buffer (HMB).
old-location : storage\storportfreehostmemorybuffer.htm
old-project : storage
ms.assetid : 686D141E-E6EA-4BB6-8556-0ECAC592E8F0
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.storportfreehostmemorybuffer, StorPortFreeHostMemoryBuffer routine [Storage Devices], storport/StorPortFreeHostMemoryBuffer, StorPortFreeHostMemoryBuffer
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
req.lib : NtosKrnl.exe
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


# StorPortFreeHostMemoryBuffer function
The <b>StorPortFreeHostMemoryBuffer</b> routine frees the physically contiguous memory
    that was allocated to be used for a Host Memory Buffer (HMB)

## Syntax

````
ULONG StorPortFreeHostMemoryBuffer(
  _In_ PVOID                                               HwDeviceExtension,
       _In_reads_(PhysicalAddressRangeCount) PACCESS_RANGE PhysicalAddressRanges,
  _In_ ULONG                                               PhysicalAddressRangeCount
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension for the host bus adapter (HBA).

`PhysicalAddressRanges`

The array of physical address ranges that make up
        the Host Memory Buffer previously allocated by  <b>StorPortAllocateHostMemoryBuffer</b>.

`PhysicalAddressRangeCount`

The number of entries in <b>PhysicalAddressRanges</b>.


## Return Value

<b>StorPortFreeHostMemoryBuffer</b> returns one of the following status codes:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The host memory buffer was successfully freed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The host memory buffer was not valid (likely already freed).

</td>
</tr>
</table>


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

<a href="https://msdn.microsoft.com/B8413B02-32A6-40AE-9DD2-C25AD2D2D45C">StorPortAllocateHostMemoryBuffer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortFreeHostMemoryBuffer routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>