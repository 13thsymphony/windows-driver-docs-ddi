---
UID: NS.ntddndis._NDIS_RSS_SET_INDIRECTION_ENTRY
title: NDIS_RSS_SET_INDIRECTION_ENTRY
author: windows-driver-content
description: The NDIS_RSS_SET_INDIRECTION_ENTRY structure represents a command to set a single indirection table entry.
old-location: netvista\ndis_rss_set_indirection_entry.htm
old-project: netvista
ms.assetid: 4430E19F-C603-4C52-8FC8-C36197FD2996
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: NDIS_RSS_SET_INDIRECTION_ENTRY, NDIS_RSS_SET_INDIRECTION_ENTRY, *PNDIS_RSS_SET_INDIRECTION_ENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.80 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_RSS_SET_INDIRECTION_ENTRY
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

# NDIS_RSS_SET_INDIRECTION_ENTRY structure



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]</p>


## -syntax

````
typedef struct _NDIS_RSS_SET_INDIRECTION_ENTRY {
  NDIS_NIC_SWITCH_ID       SwitchId;
  NDIS_NIC_SWITCH_VPORT_ID VPortId;
  ULONG                    Flags;
  USHORT                   IndirectionTableIndex;
  PROCESSOR_NUMBER         TargetProcessorNumber;
  NDIS_STATUS              EntryStatus;
} NDIS_RSS_SET_INDIRECTION_ENTRY, *PNDIS_RSS_SET_INDIRECTION_ENTRY;
````


## -struct-fields
<dl>

### -field <b>SwitchId</b>

<dd>
<p>An NDIS_NIC_SWITCH_ID value that represents the NIC switch where the VPort resides. </p>
<p>The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch. </p>
</dd>

### -field <b>VPortId</b>

<dd>
<p>An NDIS_NIC_SWITCH_VPORT_ID value that represents the VPort identifier.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>A <b>ULONG</b> value that contains a bitwise OR of flags. This member qualifies the information in this structure.</p>
<p>Possible flags are as follows:</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_RSS_SET_INDIRECTION_ENTRY_FLAG_PRIMARY_PROCESSOR"></a><a id="ndis_rss_set_indirection_entry_flag_primary_processor"></a><dl>

### -field <b>NDIS_RSS_SET_INDIRECTION_ENTRY_FLAG_PRIMARY_PROCESSOR</b>

</dl>
</td>
<td width="60%">
<p>Indicates that the <b>NDIS_RSS_SET_INDIRECTION_ENTRY</b> is referring to the primary processor of the scaling entity (in other words, a VPort in RSSv2 mode). The indirection table is not used.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_RSS_SET_INDIRECTION_ENTRY_FLAG_DEFAULT_PROCESSOR"></a><a id="ndis_rss_set_indirection_entry_flag_default_processor"></a><dl>

### -field <b>NDIS_RSS_SET_INDIRECTION_ENTRY_FLAG_DEFAULT_PROCESSOR</b>

</dl>
</td>
<td width="60%">
<p>Indicates that the <b>NDIS_RSS_SET_INDIRECTION_ENTRY</b> is referring to the default processor of the scaling entity (in other words, a VPort in RSSv2 mode). The indirection table is not used.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field <b>IndirectionTableIndex</b>

<dd>
<p>A <b>USHORT</b> value that indicates the indirection table entry being moved.</p>
</dd>

### -field <b>TargetProcessorNumber</b>

<dd>
<p>The target processor number.</p>
</dd>

### -field <b>EntryStatus</b>

<dd>
<p>An NDIS_STATUS code indicating the status of the move operation for this entry. Because <b>NDIS_RSS_SET_INDIRECTION_ENTRY</b> is used in the context of a Synchronous OID call, the miniport driver cannot return <b>NDIS_STATUS_PENDING</b> for this member.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.80 and later.</p>
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/network/receive-side-scaling-version-2-rssv2-">Receive Side Scaling Version 2 (RSSv2)</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-rss-set-indirection-table-entries">OID_GEN_RSS_SET_INDIRECTION_TABLE_ENTRIES</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80">Synchronous OID request interface in NDIS 6.80</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-rss-set-indirection-entries.md">NDIS_RSS_SET_INDIRECTION_ENTRIES</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RSS_SET_INDIRECTION_ENTRY structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
