---
UID: NF:ndis.NdisGetPoolFromNetBuffer
title: NdisGetPoolFromNetBuffer function
author: windows-driver-content
description: Call the NdisGetPoolFromNetBuffer function to get the NET_BUFFER structure pool handle that is associated with a specified NET_BUFFER structure.
old-location: netvista\ndisgetpoolfromnetbuffer.htm
old-project: netvista
ms.assetid: 64bb049a-6b8a-470f-8269-8a168761e388
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NdisGetPoolFromNetBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisGetPoolFromNetBuffer
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_NetBuffer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisGetPoolFromNetBuffer function



## -description
Call the 
  <b>NdisGetPoolFromNetBuffer</b> function to get the 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure pool handle that is associated
  with a specified NET_BUFFER structure.



## -syntax

````
NDIS_HANDLE NdisGetPoolFromNetBuffer(
  _In_ PNET_BUFFER NetBuffer
);
````


## -parameters

### -param NetBuffer [in]

A pointer to a previously allocated 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure.


## -returns
<b>NdisGetPoolFromNetBuffer</b> returns a handle to the NET_BUFFER structure pool that is associated with
     the specified NET_BUFFER structure.


## -remarks
The handle that 
    <b>NdisGetPoolFromNetBuffer</b> returns is a required parameter in calls to NDIS functions that manipulate
    
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures that are from the
    associated NET_BUFFER structure pool.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.0 and later.

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
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547985">Irql_NetBuffer_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetPoolFromNetBuffer function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

