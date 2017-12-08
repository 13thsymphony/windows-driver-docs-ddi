---
UID: NS.ntddndis._NDIS_HYPERVISOR_INFO
title: NDIS_HYPERVISOR_INFO
author: windows-driver-content
description: The NDIS_HYPERVISOR_INFO structure contains information about the hypervisor that is present on the system.
old-location: netvista\ndis_hypervisor_info.htm
old-project: netvista
ms.assetid: 847987d4-f67b-4e88-9a8d-9be4ad9be80d
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NDIS_HYPERVISOR_INFO, NDIS_HYPERVISOR_INFO, *PNDIS_HYPERVISOR_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_HYPERVISOR_INFO
req.alt-loc: Ntddndis.h
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
req.iface: 
---

# NDIS_HYPERVISOR_INFO structure



## -description

## -syntax

````
typedef struct _NDIS_HYPERVISOR_INFO {
  NDIS_OBJECT_HEADER             Header;
  ULONG                          Flags;
  NDIS_HYPERVISOR_PARTITION_TYPE PartitionType;
} NDIS_HYPERVISOR_INFO, *PNDIS_HYPERVISOR_INFO;
````


## -struct-fields
<dl>

### -field Header

<dd>
<p>The type, revision, and size of the <b>NDIS_HYPERVISOR_INFO</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a> structure.</p>
<p>The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_HYPERVISOR_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: </p>
<p></p>
<dl>

### -field NDIS_HYPERVISOR_INFO_REVISION_1

<dd>
<p>Original version for NDIS 6.20.</p>
<p>Set the <b>Size</b> member to NDIS_SIZEOF_HYPERVISOR_INFO_REVISION_1.</p>
</dd>
</dl>
</dd>

### -field Flags

<dd>
<p>A ULONG value that contains a bitwise OR of the following flag.
     </p>
<p></p>
<dl>

### -field NDIS_HYPERVISOR_INFO_FLAG_HYPERVISOR_PRESENT

<dd>
<p>Specifies that a hypervisor is present on the system.</p>
</dd>
</dl>
</dd>

### -field PartitionType

<dd>
<p>An 
     <a href="..\ntddndis\ne-ntddndis--ndis-hypervisor-partition-type.md">
     NDIS_HYPERVISOR_PARTITION_TYPE</a> enumeration value that specifies the partition type that is running
     on the hypervisor.</p>
</dd>
</dl>

## -remarks
<p>The <b>NDIS_HYPERVISOR_INFO</b> structure specifies the hypervisor information that is returned by the 
    <a href="..\ndis\nf-ndis-ndisgethypervisorinfo.md">NdisGetHypervisorInfo</a> function.</p>

<p>NDIS drivers pass this structure to the 
    <b>NdisGetHypervisorInfo</b> function.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.20 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\ntddndis\ne-ntddndis--ndis-hypervisor-partition-type.md">NDIS_HYPERVISOR_PARTITION_TYPE</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisgethypervisorinfo.md">NdisGetHypervisorInfo Function</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_HYPERVISOR_INFO structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
