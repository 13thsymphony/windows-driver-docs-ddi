---
UID: NF.ndis.NdisEqualMemory
title: NdisEqualMemory macro
author: windows-driver-content
description: The NdisEqualMemory function compares a specified number of characters in one block of memory with the same number of characters in a second block of memory.
old-location: netvista\ndisequalmemory.htm
old-project: netvista
ms.assetid: 5417b821-b51d-4789-8380-f93d113f42d3
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisEqualMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlEqualMemory instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisEqualMemory
req.alt-loc: ndis.h
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
---

# NdisEqualMemory macro



## -description
The 
  <b>NdisEqualMemory</b> function compares a specified number of characters in one block of memory with the
  same number of characters in a second block of memory.



## -syntax

````
ULONG NdisEqualMemory(
   const VOID  *Source1,
   const VOID  *Source2,
         ULONG Length
);
````


## -parameters

### -param Source1 

A pointer to the first block of memory to be compared.


### -param Source2 

A pointer to the second block of memory to be compared.


### -param Length 

The number of bytes to be compared.


## -remarks
<b>NdisEqualMemory</b> compares two blocks of memory and uses the value that is specified in the 
    <i>Length</i> parameter for both blocks. The data type of anything in the compared memory blocks is
    irrelevant.

Callers of 
    <b>NdisEqualMemory</b> can be running at IRQL &lt;= DISPATCH_LEVEL if both memory blocks are resident. If
    either block is pageable, callers must be running at IRQL &lt; DISPATCH_LEVEL.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use <a href="kernel.rtlequalmemory">RtlEqualMemory</a> instead.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
See Remarks section

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_irql_miscellaneous_function">Irql_Miscellaneous_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndisallocatememorywithtagpriority">
   NdisAllocateMemoryWithTagPriority</a>
</dt>
<dt>
<a href="kernel.rtlfillmemory">RtlFillMemory</a>
</dt>
<dt>
<a href="netvista.ndisfreememory">NdisFreeMemory</a>
</dt>
<dt>
<a href="kernel.rtlcopymemory">RtlCopyMemory</a>
</dt>
<dt>
<a href="kernel.rtlzeromemory">RtlZeroMemory</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisEqualMemory macro%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

