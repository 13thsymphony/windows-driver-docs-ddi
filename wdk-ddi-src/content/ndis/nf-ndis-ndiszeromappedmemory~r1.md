---
UID: NF.ndis.NdisZeroMappedMemory~r1
title: NdisZeroMappedMemory
author: windows-driver-content
description: NdisZeroMappedMemory fills a block of memory that was mapped with a preceding call to NdisMMapIoSpace with zeros.
old-location: netvista\ndiszeromappedmemory.htm
old-project: netvista
ms.assetid: 210e20a5-c101-4005-97fb-e549ff97e7ce
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: NdisZeroMappedMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   NdisZeroMappedMemory (NDIS
   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   NdisZeroMappedMemory (NDIS
   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisZeroMappedMemory
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.iface: 
---

# NdisZeroMappedMemory function



## -description
<p><b>NdisZeroMappedMemory</b> fills a block of memory that was mapped with a preceding call to 
  <b>NdisMMapIoSpace</b> with zeros.</p>


## -syntax

````
VOID NdisZeroMappedMemory(
  _In_ PVOID Destination,
  _In_ ULONG Length
);
````


## -parameters
<dl>

### -param <i>Destination</i> [in]

<dd>
<p>Specifies the base virtual address of a block of mapped memory.</p>
</dd>

### -param <i>Length</i> [in]

<dd>
<p>Specifies the number of bytes to be filled with zeros.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>A miniport driver can call 
    <b>NdisZeroMappedMemory</b> to zero-initialize mapped device memory. The given 
    <i>Destination</i> and 
    <i>Length</i> must be a proper subrange of the range specified when the driver called 
    <a href="https://msdn.microsoft.com/library/windows/hardware/hh975119">NdisMMapIoSpace</a>.</p>

<p><b>NdisZeroMappedMemory</b> is optimized, and a miniport driver can call this function any time that it
    needs to clear a mapped memory range.</p>

<p>A miniport driver can call 
    <b>NdisZeroMappedMemory</b> to zero-initialize mapped device memory. The given 
    <i>Destination</i> and 
    <i>Length</i> must be a proper subrange of the range specified when the driver called 
    <a href="https://msdn.microsoft.com/library/windows/hardware/hh975119">NdisMMapIoSpace</a>.</p>

<p><b>NdisZeroMappedMemory</b> is optimized, and a miniport driver can call this function any time that it
    needs to clear a mapped memory range.</p>

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
<p>Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/8e276dca-733f-43e3-b5dc-a3d7d696e2a9">NdisZeroMappedMemory (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisZeroMappedMemory (NDIS
   5.1)</b>) in Windows XP.</p>
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
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975119">NdisMMapIoSpace</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564698">NdisZeroMemory</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisZeroMappedMemory function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
