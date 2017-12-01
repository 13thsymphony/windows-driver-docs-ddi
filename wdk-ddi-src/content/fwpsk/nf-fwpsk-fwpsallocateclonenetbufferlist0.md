---
UID: NF.fwpsk.FwpsAllocateCloneNetBufferList0
title: FwpsAllocateCloneNetBufferList0
author: windows-driver-content
description: The FwpsAllocateCloneNetBufferList0 function allocates a NET_BUFFER_LIST structure that is a clone of an existing NET_BUFFER_LIST structure.Note  FwpsAllocateCloneNetBufferList0 is a specific version of FwpsAllocateCloneNetBufferList.
old-location: netvista\fwpsallocateclonenetbufferlist0.htm
old-project: netvista
ms.assetid: 72759748-fac6-45b9-9a81-ab71e6e7c3ef
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: FwpsAllocateCloneNetBufferList0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FwpsAllocateCloneNetBufferList0
req.alt-loc: fwpkclnt.lib,fwpkclnt.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# FwpsAllocateCloneNetBufferList0 function



## -description
<p>The 
  <b>FwpsAllocateCloneNetBufferList0</b> function allocates a 
  <a href="..\ndis\ns-ndis--net-buffer-list.md">NET_BUFFER_LIST</a> structure that is a clone of an existing
  <b>NET_BUFFER_LIST</b> structure.</p>


## -syntax

````
NTSTATUS NTAPI FwpsAllocateCloneNetBufferList0(
  _Inout_  NET_BUFFER_LIST *originalNetBufferList,
  _In_opt_ NDIS_HANDLE     netBufferListPoolHandle,
  _In_opt_ NDIS_HANDLE     netBufferPoolHandle,
  _In_     ULONG           allocateCloneFlags,
  _Out_    NET_BUFFER_LIST **netBufferList
);
````


## -parameters
<dl>

### -param <i>originalNetBufferList</i> [in, out]

<dd>
<p>A pointer to the original 
     <a href="..\ndis\ns-ndis--net-buffer-list.md">NET_BUFFER_LIST</a> structure that is being
     cloned.</p>
</dd>

### -param <i>netBufferListPoolHandle</i> [in, optional]

<dd>
<p>A 
     <a href="..\ndis\ns-ndis--net-buffer-list.md">NET_BUFFER_LIST</a> pool handle that was
     obtained from a previous call to the 
     <a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">
     NdisAllocateNetBufferListPool</a> function. This parameter is optional and can be <b>NULL</b>.</p>
</dd>

### -param <i>netBufferPoolHandle</i> [in, optional]

<dd>
<p>A 
     <a href="..\ndis\ns-ndis--net-buffer.md">NET_BUFFER</a> pool handle that was obtained from a
     previous call to the 
     <a href="..\ndis\nf-ndis-ndisallocatenetbufferpool.md">NdisAllocateNetBufferPool</a> function. This parameter is optional and can be <b>NULL</b>.</p>
</dd>

### -param <i>allocateCloneFlags</i> [in]

<dd>
<p>There are currently no flags defined for this function. Callout drivers should set this parameter
     to zero.</p>
</dd>

### -param <i>netBufferList</i> [out]

<dd>
<p>A pointer to a variable that receives a pointer to the clone 
     <a href="..\ndis\ns-ndis--net-buffer-list.md">NET_BUFFER_LIST</a> structure.</p>
</dd>
</dl>

## -returns
<p>The 
     <b>FwpsAllocateCloneNetBufferList0</b> function returns one of the following NTSTATUS codes.</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The clone 
       <a href="..\ndis\ns-ndis--net-buffer-list.md">NET_BUFFER_LIST</a> structure was
       successfully allocated.</p><dl>
<dt><b>Other status codes</b></dt>
</dl><p>An error occurred.</p>

<p> </p>

## -remarks
<p>A callout driver calls the 
    <b>FwpsAllocateCloneNetBufferList0</b> function to allocate a clone 
    <a href="..\ndis\ns-ndis--net-buffer-list.md">NET_BUFFER_LIST</a> structure of an existing
    NET_BUFFER_LIST structure.</p>

<p>This function is a wrapper around the 
    <a href="..\ndis\nf-ndis-ndisallocateclonenetbufferlist.md">
    NdisAllocateCloneNetBufferList</a> function, but it is specialized for use by WFP 
    <a href="NULL">packet injection functions</a>.</p>

<p>If the clone NET_BUFFER_LIST structure should have attributes that are associated with a specific pool,
    the callout driver must specify the pool handle in the 
    <i>NetBufferListPoolHandle</i> or 
    <i>NetBufferPoolHandle</i> parameter. If these parameters are <b>NULL</b>, the default pool preallocated by NDIS
    is used.</p>

<p>The clone NET_BUFFER_LIST structure describes the same data that is described by the original
    NET_BUFFER_LIST structure. The 
    <b>FwpsAllocateCloneNetBufferList0</b> function does not copy the data that is described by the original
    MDLs to new data buffers. Instead, the clone NET_BUFFER_LIST structure references the original data
    buffers. The clone NET_BUFFER_LIST structure does not include an initial 
    <a href="..\ndis\ns-ndis--net-buffer-list-context.md">
    NET_BUFFER_LIST_CONTEXT</a> structure.</p>

<p>This function sets the 
    <b>ParentNetBufferList</b> member of the newly created clone NET_BUFFER_LIST structure to point to the
    parent NET_BUFFER_LIST structure. The parent structure's 
    <b>ChildRefCount</b> member is incremented by 1.</p>

<p>A callout driver can modify the clone NET_BUFFER_LIST structure and inject it into the network stack
    in place of the original NET_BUFFER_LIST structure by calling the 
    <a href="NULL">packet injection functions</a>. After
    the data described by the clone NET_BUFFER_LIST structure has been successfully injected into the network
    stack, the callout driver frees the clone NET_BUFFER_LIST structure by calling the 
    <a href="..\fwpsk\nf-fwpsk-fwpsfreeclonenetbufferlist0.md">FwpsFreeCloneNetBufferList0</a> function.</p>

<p>A callout driver can insert or replace individual net buffers (<a href="..\ndis\ns-ndis--net-buffer.md">NET_BUFFER</a>) or MDLs inside the clone net buffer
    list. Such a driver must also undo the modifications before it calls the 
    <a href="..\fwpsk\nf-fwpsk-fwpsfreeclonenetbufferlist0.md">
    FwpsFreeCloneNetBufferList0</a> function.</p>

<p>A callout driver must not hold cloned packets indefinitely. A cloned packet can interfere with power
     management operations on an idle computer.</p>

<p>The intended use for cloned packets in WFP is to get clarification from a user-mode application or
     other relatively fast operation. The callout driver must not hold cloned packets while, for example,
     waiting for user input, or waiting for web service clearance, or waiting for any other operation that
     might take an arbitrary amount of time.</p>

<p>If the callout driver needs to wait for a potentially lengthy operation, it makes a deep copy of
     the packet using 
     <a href="..\fwpsk\nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0.md">
     FwpsAllocateNetBufferAndNetBufferList0</a>, and it blocks and absorbs the original packet.</p>

<p>Callout drivers should always return held packets as quickly as possible.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows Vista.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Fwpkclnt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsfreeclonenetbufferlist0.md">FwpsFreeCloneNetBufferList0</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">
   NdisAllocateNetBufferListPool</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatenetbufferpool.md">NdisAllocateNetBufferPool</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--net-buffer.md">NET_BUFFER</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--net-buffer-list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--net-buffer-list-context.md">NET_BUFFER_LIST_CONTEXT</a>
</dt>
<dt>
<a href="NULL">Packet Injection Functions</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsAllocateCloneNetBufferList0 function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
