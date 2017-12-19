---
UID: NS.NTDDNDIS._NDIS_NDK_STATISTICS_INFO
title: _NDIS_NDK_STATISTICS_INFO
author: windows-driver-content
description: The NDIS_NDK_STATISTICS_INFO structure contains the NDK statistics.
old-location: netvista\ndis_ndk_statistics_info.htm
old-project: NetVista
ms.assetid: F3FA3790-0754-4D5E-9F27-8ECD71278520
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_NDK_STATISTICS_INFO, NDIS_NDK_STATISTICS_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_NDK_STATISTICS_INFO
req.alt-loc: ntddndis.h
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
---

# _NDIS_NDK_STATISTICS_INFO structure



## -description
The <b>NDIS_NDK_STATISTICS_INFO</b> structure contains the NDK statistics.



## -syntax

````
typedef struct _NDIS_NDK_STATISTICS_INFO {
  NDIS_OBJECT_HEADER            Header;
  NDIS_NDK_PERFORMANCE_COUNTERS CounterSet;
} NDIS_NDK_STATISTICS_INFO, *PNDIS_NDK_STATISTICS_INFO;
````


## -struct-fields

### -field Header

An <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure that describes this <b>NDIS_NDK_STATISTICS_INFO</b> structure. Set the members of the <b>NDIS_OBJECT_HEADER</b> structure as follows:

<ul>
<li>Set the <b>Type</b> member to <b>NDIS_OBJECT_TYPE_DEFAULT</b>.</li>
<li>Set the <b>Revision</b> member to <b>NDIS_NDK_STATISTICS_INFO_REVISION_1</b>.</li>
<li>Set the <b>Size</b> member to <b>NDIS_SIZEOF_NDK_STATISTICS_INFO_REVISION_1</b>.</li>
</ul>

### -field CounterSet

An <a href="netvista.ndis_ndk_performance_counters">NDIS_NDK_PERFORMANCE_COUNTERS</a> structure that contains the NDK performance counters.


## -remarks
The <b>NDIS_NDK_STATISTICS_INFO</b> structure is returned with the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451813">OID_NDK_STATISTICS</a> OID. The <b>InformationBuffer</b> member of the <a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a> structure contains a pointer to this structure.



The NDK-capable miniport driver is required to fill in the <b>CounterSet</b> member, which is an <a href="netvista.ndis_ndk_performance_counters">NDIS_NDK_PERFORMANCE_COUNTERS</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
None supported

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.30 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndis_ndk_performance_counters">NDIS_NDK_PERFORMANCE_COUNTERS</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451813">OID_NDK_STATISTICS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDIS_NDK_STATISTICS_INFO structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

