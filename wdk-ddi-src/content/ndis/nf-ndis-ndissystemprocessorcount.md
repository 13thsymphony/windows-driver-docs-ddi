---
UID : NF:ndis.NdisSystemProcessorCount
title : NdisSystemProcessorCount function
author : windows-driver-content
description : The NdisSystemProcessorCount function determines whether the caller is running on a uniprocessor or multiprocessor computer.
old-location : netvista\ndissystemprocessorcount.htm
old-project : netvista
ms.assetid : 17c7b02d-3d32-4056-9baa-2fef74765da3
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : NdisSystemProcessorCount
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use NdisGroupMaxProcessorCount.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NdisSystemProcessorCount
req.alt-loc : ndis.lib,ndis.dll
req.ddi-compliance : Irql_Miscellaneous_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisSystemProcessorCount function
The 
  <b>NdisSystemProcessorCount</b> function determines whether the caller is running on a uniprocessor or
  multiprocessor computer.

## Syntax

````
CCHAR NdisSystemProcessorCount(void);
````

## Parameters

This function has no parameters.

## Return Value

<b>NdisSystemProcessorCount</b> returns the number of processors in the computer.

<b>NdisSystemProcessorCount</b> returns the number of processors in the computer.

<b>NdisSystemProcessorCount</b> returns the number of processors in the computer.

## Remarks

An NDIS driver can call the 
    <b>NdisSystemProcessorCount</b> function to retrieve the maximum number of processors in the local
    computer. To retrieve the number of currently active processors, the driver must call the 
    <a href="..\ndis\nf-ndis-ndissystemactiveprocessorcount.md">
    NdisSystemActiveProcessorCount</a> function.

<b>NdisSystemProcessorCount</b> is similar to the 
    <a href="..\wdm\nf-wdm-kequerymaximumprocessorcount.md">
    KeQueryMaximumProcessorCount</a> function.

The value that 
    <b>NdisSystemProcessorCount</b> returns does not change at runtime.

If your code uses an array of buffers, one buffer for each processor, you must decide whether to have
    a statically sized array based on 
    <b>NdisSystemProcessorCount</b> or a dynamically sized array based on 
    <a href="..\ndis\nf-ndis-ndissystemactiveprocessorcount.md">NdisSystemActiveProcessorCount</a>.

To optimize your code based on the number of processors, you must use a resizable structure. In this
    case, use 
    <a href="..\ndis\nf-ndis-ndissystemactiveprocessorcount.md">NdisSystemActiveProcessorCount</a>.

If you are not optimizing and if the data structures that result from using the maximum processor
    count are relatively small, a resizable structure is not necessary. In this case, use 
    <b>NdisSystemProcessorCount</b> to determine the size for a static array.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_Miscellaneous_Function |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/gg156036.aspx">DriverEntry of NDIS Protocol
   Drivers</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kequerymaximumprocessorcount.md">KeQueryMaximumProcessorCount</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisgroupmaxprocessorcount.md">NdisGroupMaxProcessorCount</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndissystemactiveprocessorcount.md">
   NdisSystemActiveProcessorCount</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisSystemProcessorCount function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>