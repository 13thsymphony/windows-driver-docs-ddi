---
UID: NF.ndis.NdisGetCurrentProcessorCpuUsage
title: NdisGetCurrentProcessorCpuUsage
author: windows-driver-content
description: The NdisGetCurrentProcessorCpuUsage function returns the average amount of activity on the current processor since boot as a percentage.Note  This function is deprecated.
old-location: netvista\ndisgetcurrentprocessorcpuusage.htm
old-project: netvista
ms.assetid: 03f1559c-83a7-478c-a616-ebe6002cb724
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NdisGetCurrentProcessorCpuUsage
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Deprecated for NDIS 6.0 and later drivers in Windows Vista and later. Deprecated for NDIS 5.1 drivers (see       NdisGetCurrentProcessorCpuUsage (NDIS 5.1)) in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisGetCurrentProcessorCpuUsage
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
req.iface: 
---

# NdisGetCurrentProcessorCpuUsage function



## -description
<p>The 
  <b>NdisGetCurrentProcessorCpuUsage</b> function returns the  average amount of activity on the current processor since boot as a
  percentage.</p>


## -syntax

````
VOID NdisGetCurrentProcessorCpuUsage(
  _Out_ PULONG pCpuUsage
);
````


## -parameters
<dl>

### -param pCpuUsage [out]

<dd>
<p>A pointer to a caller-supplied variable that receives the average usage of the current processor since boot, expressed as a percentage.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The <b>NdisGetCurrentProcessorCpuUsage</b> function returns the average amount of activity on the current processor since the last boot, not the current usage level. This information is not particularly useful. Therefore, we recommend that you don't use <b>NdisGetCurrentProcessorCpuUsage</b> in your driver.</p>

<p>As an alternative, you can use <a href="..\ndis\nf-ndis-ndisgetcurrentprocessorcounts.md">NdisGetCurrentProcessorCounts</a> to see whether the processor is currently loaded.</p>

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
<p>Deprecated for NDIS 6.0 and later drivers in Windows Vista and later. Deprecated for NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/21be6dc4-86c9-44b5-a425-400e4ff77e24">
   NdisGetCurrentProcessorCpuUsage (NDIS 5.1)</a>) in Windows XP and later.</p>
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
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
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
<a href="..\ndis\nf-ndis-ndisgetcurrentprocessorcounts.md">NdisGetCurrentProcessorCounts</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetCurrentProcessorCpuUsage function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
