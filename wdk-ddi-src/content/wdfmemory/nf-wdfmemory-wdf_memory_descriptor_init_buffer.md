---
UID : NF:wdfmemory.WDF_MEMORY_DESCRIPTOR_INIT_BUFFER
title : WDF_MEMORY_DESCRIPTOR_INIT_BUFFER function
author : windows-driver-content
description : The WDF_MEMORY_DESCRIPTOR_INIT_BUFFER function initializes a WDF_MEMORY_DESCRIPTOR structure so that it describes a specified buffer.
old-location : wdf\wdf_memory_descriptor_init_buffer.htm
old-project : wdf
ms.assetid : 16e1b0cb-8543-4700-8f8c-d7301c6de622
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.wdf_memory_descriptor_init_buffer, WDF_MEMORY_DESCRIPTOR_INIT_BUFFER, WDF_MEMORY_DESCRIPTOR_INIT_BUFFER function, wdfmemory/WDF_MEMORY_DESCRIPTOR_INIT_BUFFER, kmdf.wdf_memory_descriptor_init_buffer, DFMemoryObjectRef_706a9ee6-c0f1-4cb4-a887-cbb535d94d17.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfmemory.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA
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
req.typenames : WDF_MEMORY_DESCRIPTOR_TYPE
req.product : Windows 10 or later.
---


# WDF_MEMORY_DESCRIPTOR_INIT_BUFFER function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_MEMORY_DESCRIPTOR_INIT_BUFFER</b> function initializes a <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure so that it describes a specified buffer.

## Syntax

````
VOID WDF_MEMORY_DESCRIPTOR_INIT_BUFFER(
  _Out_ PWDF_MEMORY_DESCRIPTOR Descriptor,
  _In_  PVOID                  Buffer,
  _In_  ULONG                  BufferLength
);
````

## Parameters

`Descriptor`

A pointer to a <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure.

`Buffer`

A pointer to a memory buffer.

`BufferLength`

The size, in bytes, of the memory buffer that <i>Buffer</i> points to.


## Return Value

None

## Remarks

The <b>WDF_MEMORY_DESCRIPTOR_INIT_BUFFER</b> function zeros the specified <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure and sets the structure's <b>Type</b> member to <b>WdfMemoryDescriptorTypeBuffer</b>. Then it sets the structure's <b>u.BufferType.Buffer</b> and <b>u.BufferType.Length</b> members to the values that the <i>Buffer</i> and <i>BufferLength</i> parameters specify, respectively.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfmemory.h (include Wdf.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** | BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA |

## See Also

<a href="..\wdfmemory\nf-wdfmemory-wdf_memory_descriptor_init_mdl.md">WDF_MEMORY_DESCRIPTOR_INIT_MDL</a>

<a href="..\wdfmemory\nf-wdfmemory-wdf_memory_descriptor_init_handle.md">WDF_MEMORY_DESCRIPTOR_INIT_HANDLE</a>

<a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_MEMORY_DESCRIPTOR_INIT_BUFFER function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>