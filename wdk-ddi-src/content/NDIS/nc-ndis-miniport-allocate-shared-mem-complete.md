---
UID: NC.ndis.MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE
title: MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE
author: windows-driver-content
description: NDIS calls a miniport driver's MiniportSharedMemoryAllocateComplete function to complete a shared memory allocation request that the miniport driver started by calling the NdisMAllocateSharedMemoryAsyncEx function.
old-location: netvista\miniportsharedmemoryallocatecomplete.htm
ms.assetid: d102a001-960c-4fe6-af2d-d740bba744b1
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MiniportSharedMemoryAllocateComplete
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
ms.keywords: RxNameCacheInitialize
req.iface: 
---

# MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE callback



## -description
<p>NDIS calls a miniport driver's 
   <i>MiniportSharedMemoryAllocateComplete</i> function to complete a shared memory allocation request that
   the miniport driver started by calling the 
   <a href="https://msdn.microsoft.com/ccbe98ca-7da9-4159-ac1a-c25ec6745ff4">
   NdisMAllocateSharedMemoryAsyncEx</a> function.</p>


## -prototype

````
MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE MiniportSharedMemoryAllocateComplete;

VOID MiniportSharedMemoryAllocateComplete(
  _In_ NDIS_HANDLE            MiniportAdapterContext,
  _In_ PVOID                  VirtualAddress,
  _In_ PNDIS_PHYSICAL_ADDRESS PhysicalAddress,
  _In_ ULONG                  Length,
  _In_ PVOID                  Context
)
{ ... }
````


## -parameters
<dl>

### -param <i>MiniportAdapterContext</i> [in]

<dd>
<p>The handle to a context area allocated by the miniport driver in which the driver maintains state
     information for a NIC. The driver allocates this context area in the 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.</p>
</dd>

### -param <i>VirtualAddress</i> [in]

<dd>
<p>The base virtual address of the shared memory that the miniport driver allocated by calling 
     <b>NdisMAllocateSharedMemoryAsyncEx</b>. 
     <i>VirtualAddress</i> is <b>NULL</b> if the allocation attempt failed.</p>
</dd>

### -param <i>PhysicalAddress</i> [in]

<dd>
<p>The base physical address for the NIC to use that is mapped to the address that the 
     <i>VirtualAddress</i> parameter specifies.</p>
</dd>

### -param <i>Length</i> [in]

<dd>
<p>The number of bytes that 
     <b>NdisMAllocateSharedMemoryAsyncEx</b> allocated.</p>
</dd>

### -param <i>Context</i> [in]

<dd>
<p>A pointer to a context area that the miniport driver specified in the preceding call to 
     <b>NdisMAllocateSharedMemoryAsyncEx</b>.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p><i>MiniportAllocateSharedMemoryComplete</i> is an optional function for miniport drivers. A miniport
    driver registers a 
    <i>MiniportAllocateSharedMemoryComplete</i> function in the NDIS_SG_DMA_DESCRIPTION structure that the
    driver passed to the 
    <a href="https://msdn.microsoft.com/90ce64a2-9140-4b5f-88aa-b4f01a3d0c6f">
    NdisMRegisterScatterGatherDma</a> function.</p>

<p>Miniport drivers call 
    <a href="https://msdn.microsoft.com/ccbe98ca-7da9-4159-ac1a-c25ec6745ff4">
    NdisMAllocateSharedMemoryAsyncEx</a> to allocate shared memory. If 
    <b>NdisMAllocateSharedMemoryAsyncEx</b> returns NDIS_STATUS_PENDING, NDIS calls 
    <i>MiniportAllocateSharedMemoryComplete</i> to pass the memory to the miniport driver.</p>

<p>NDIS calls 
    <i>MiniportSharedMemoryAllocateComplete</i> at IRQL PASSIVE_LEVEL.</p>

<p>To define a <i>MiniportSharedMemoryAllocateComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>MiniportSharedMemoryAllocateComplete</i> function that is named "MySharedMemoryAllocateComplete", use the <b>MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. </p>

<p><i>MiniportAllocateSharedMemoryComplete</i> is an optional function for miniport drivers. A miniport
    driver registers a 
    <i>MiniportAllocateSharedMemoryComplete</i> function in the NDIS_SG_DMA_DESCRIPTION structure that the
    driver passed to the 
    <a href="https://msdn.microsoft.com/90ce64a2-9140-4b5f-88aa-b4f01a3d0c6f">
    NdisMRegisterScatterGatherDma</a> function.</p>

<p>Miniport drivers call 
    <a href="https://msdn.microsoft.com/ccbe98ca-7da9-4159-ac1a-c25ec6745ff4">
    NdisMAllocateSharedMemoryAsyncEx</a> to allocate shared memory. If 
    <b>NdisMAllocateSharedMemoryAsyncEx</b> returns NDIS_STATUS_PENDING, NDIS calls 
    <i>MiniportAllocateSharedMemoryComplete</i> to pass the memory to the miniport driver.</p>

<p>NDIS calls 
    <i>MiniportSharedMemoryAllocateComplete</i> at IRQL PASSIVE_LEVEL.</p>

<p>To define a <i>MiniportSharedMemoryAllocateComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>MiniportSharedMemoryAllocateComplete</i> function that is named "MySharedMemoryAllocateComplete", use the <b>MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/ccbe98ca-7da9-4159-ac1a-c25ec6745ff4">
   NdisMAllocateSharedMemoryAsyncEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/90ce64a2-9140-4b5f-88aa-b4f01a3d0c6f">
   NdisMRegisterScatterGatherDma</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE callback function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
