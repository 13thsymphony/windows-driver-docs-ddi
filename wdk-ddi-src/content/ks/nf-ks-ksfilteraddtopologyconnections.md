---
UID: NF.ks.KsFilterAddTopologyConnections
title: KsFilterAddTopologyConnections function
author: windows-driver-content
description: The KsFilterAddTopologyConnections function adds new topology connections to a filter.
old-location: stream\ksfilteraddtopologyconnections.htm
old-project: stream
ms.assetid: 32a61103-5f2f-4b73-a299-bf6a14c3bec9
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsFilterAddTopologyConnections
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsFilterAddTopologyConnections
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# KsFilterAddTopologyConnections function



## -description
The<b> KsFilterAddTopologyConnections</b> function adds new topology connections to a filter.



## -syntax

````
NTSTATUS KsFilterAddTopologyConnections(
  _In_       PKSFILTER             Filter,
  _In_       ULONG                 NewConnectionsCount,
  _In_ const KSTOPOLOGY_CONNECTION *NewTopologyConnections
);
````


## -parameters

### -param Filter [in]

<i>A pointer</i> to the <a href="stream.ksfilter">KSFILTER</a> to which to add the new connections.


### -param NewConnectionsCount [in]

The number of connections in <i>NewTopologyConnections</i>.


### -param NewTopologyConnections [in]

A pointer to an array of <a href="stream.kstopology_connection">KSTOPOLOGY_CONNECTION</a> structures containing the new topology connections.


## -returns
<b>KsFilterAddTopologyConnections </b>returns STATUS_SUCCESS or an error code indicating failure of the attempt to add topology connections.


## -remarks
Note that the filter control mutex must be held before calling this function.

For more information about mutexes, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.


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
Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksfilter">KSFILTER</a>
</dt>
<dt>
<a href="stream.kstopology_connection">KSTOPOLOGY_CONNECTION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterAddTopologyConnections function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

