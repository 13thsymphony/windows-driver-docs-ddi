---
UID: NF:wdfmemory.WdfMemoryAssignBuffer
title: WdfMemoryAssignBuffer function
author: windows-driver-content
description: The WdfMemoryAssignBuffer method assigns a specified buffer to a memory object that a driver created by calling WdfMemoryCreatePreallocated.
old-location: wdf\wdfmemoryassignbuffer.htm
old-project: wdf
ms.assetid: f57fe6ac-87ad-4db8-a715-816885b87d68
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFMemoryObjectRef_c2bf3437-5c1e-44d6-97ab-6ede16f7bc53.xml, WdfMemoryAssignBuffer, WdfMemoryAssignBuffer method, kmdf.wdfmemoryassignbuffer, wdf.wdfmemoryassignbuffer, wdfmemory/WdfMemoryAssignBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA, DriverCreate, MemAfterReqCompletedIntIoctlA, MemAfterReqCompletedIoctlA, MemAfterReqCompletedReadA, MemAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfMemoryAssignBuffer
product:
- Windows
targetos: Windows
req.typenames: WDF_MEMORY_DESCRIPTOR_TYPE
req.product: Windows 10 or later.
---


# WdfMemoryAssignBuffer function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfMemoryAssignBuffer</b> method assigns a specified buffer to a memory object that a driver created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548712">WdfMemoryCreatePreallocated</a>.

## Syntax

```
NTSTATUS WdfMemoryAssignBuffer(
  WDFMEMORY Memory,
  PVOID     Buffer,
  size_t    BufferSize
);
```

## Parameters

`Memory`

A handle to a framework memory object that was obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548712">WdfMemoryCreatePreallocated</a>.

`Buffer`

A pointer to a driver-supplied buffer.

`BufferSize`

The nonzero size, in bytes, of the buffer that <i>Buffer</i> points to.


## Return Value

<b>WdfMemoryAssignBuffer</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

The method can assign a buffer to a memory object that <a href="https://msdn.microsoft.com/library/windows/hardware/ff548712">WdfMemoryCreatePreallocated</a> created, but not to a memory object that <a href="https://msdn.microsoft.com/library/windows/hardware/ff548706">WdfMemoryCreate</a> created.

The buffer that the <i>Buffer</i> parameter points to can be allocated from the pageable or non-pageable memory pool. If the driver allocates the buffer from the pageable pool, or if the buffer is from pageable pool because it came from a user-mode application, the driver must access the buffer only at IRQL &lt; DISPATCH_LEVEL. (Note that the driver's <a href="https://msdn.microsoft.com/aba2efca-7d1f-4594-af65-13356f0e3f8b">EvtCleanupCallback</a> and <a href="https://msdn.microsoft.com/4c3b08d2-bb25-40bd-b2fc-1b9ea2d452b3">EvtDestroyCallback</a> callback functions, if provided, can be called at IRQL &lt;= DISPATCH_LEVEL.)

For more information about framework memory objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-memory-buffers">Using Memory Buffers</a>.


#### Examples

The following code example allocates a buffer and then assigns the buffer to a framework memory object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PVOID  pNewBuffer = NULL;

pNewBuffer = ExAllocatePoolWithTag(
                                   NonPagedPool,
                                   NEW_BUFFER_SIZE,
                                   MY_DRIVER_TAG
                                   );
if (pNewBuffer == NULL){
    goto Error;
}

status = WdfMemoryAssignBuffer(
                               memHandle,
                               pNewBuffer,
                               NEW_BUFFER_SIZE
                               );</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfmemory.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | Any level |
| **DDI compliance rules** | BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA, DriverCreate, MemAfterReqCompletedIntIoctlA, MemAfterReqCompletedIoctlA, MemAfterReqCompletedReadA, MemAfterReqCompletedWriteA |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548712">WdfMemoryCreatePreallocated</a>