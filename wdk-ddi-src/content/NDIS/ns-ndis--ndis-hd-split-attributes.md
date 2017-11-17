---
UID: NS.ndis._NDIS_HD_SPLIT_ATTRIBUTES
title: NDIS_HD_SPLIT_ATTRIBUTES
author: windows-driver-content
description: The NDIS_HD_SPLIT_ATTRIBUTES structure defines header-data split attributes, if any, that are associated with a miniport adapter.
old-location: netvista\ndis_hd_split_attributes.htm
ms.assetid: c3e28d66-1fe8-4cb0-ada0-4292387da19a
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_HD_SPLIT_ATTRIBUTES
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
req.irql: See Remarks section
ms.keywords: NDIS_HD_SPLIT_ATTRIBUTES, NDIS_HD_SPLIT_ATTRIBUTES, *PNDIS_HD_SPLIT_ATTRIBUTES
req.iface: 
---

# NDIS_HD_SPLIT_ATTRIBUTES structure



## -description
<p>The NDIS_HD_SPLIT_ATTRIBUTES structure defines header-data split attributes, if any, that are
  associated with a miniport adapter.</p>


## -syntax

````
typedef struct _NDIS_HD_SPLIT_ATTRIBUTES {
  NDIS_OBJECT_HEADER Header;
  ULONG              HardwareCapabilities;
  ULONG              CurrentCapabilities;
  ULONG              HDSplitFlags;
  ULONG              BackfillSize;
  ULONG              MaxHeaderSize;
} NDIS_HD_SPLIT_ATTRIBUTES, *PNDIS_HD_SPLIT_ATTRIBUTES;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     provider characteristics structure (NDIS_HD_SPLIT_ATTRIBUTES). The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_HD_SPLIT_ATTRIBUTES, the 
     <b>Revision</b> member to NDIS_OBJECT_HD_SPLIT_ATTRIBUTES_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_HD_SPLIT_ATTRIBUTES_REVISION_1.</p>
</dd>

### -field <b>HardwareCapabilities</b>

<dd>
<p>The header-data split hardware capabilities that the miniport adapter supports. These capabilities
     should include capabilities that are currently disabled by INF file settings or through the 
     <b>Advanced</b> properties page. The value of 
     <b>HardwareCapabilities</b> is a bitwise OR of the following flags:
     </p>
<p></p>
<dl>

### -field <a id="NDIS_HD_SPLIT_CAPS_SUPPORTS_HEADER_DATA_SPLIT"></a><a id="ndis_hd_split_caps_supports_header_data_split"></a>NDIS_HD_SPLIT_CAPS_SUPPORTS_HEADER_DATA_SPLIT

<dd>
<p>The miniport adapter can split the header and data into separate MDLs that meet the requirements
       for header-data split support.</p>
</dd>

### -field <a id="NDIS_HD_SPLIT_CAPS_SUPPORTS_IPV4_OPTIONS"></a><a id="ndis_hd_split_caps_supports_ipv4_options"></a>NDIS_HD_SPLIT_CAPS_SUPPORTS_IPV4_OPTIONS

<dd>
<p>The miniport adapter can split IPv4 Ethernet frames that include IPv4 options. The miniport
       adapter can support splitting some IPv4 options while not splitting others. 
       </p>
<div class="alert"><b>Note</b>  The NIC must not split IPv4 frames that contain unsupported IPv4 options. If an
       IPv4 frame is split, the header portion of the split frame must contain the entire IPv4 header and all
       of the IPv4 options that are present.</div>
<div> </div>
</dd>

### -field <a id="NDIS_HD_SPLIT_CAPS_SUPPORTS_IPV6_EXTENSION_HEADERS"></a><a id="ndis_hd_split_caps_supports_ipv6_extension_headers"></a>NDIS_HD_SPLIT_CAPS_SUPPORTS_IPV6_EXTENSION_HEADERS

<dd>
<p>The miniport adapter can split IPv6 Ethernet frames that include IPv6 extension headers. The
       miniport adapter can support some IPv6 extension headers while not supporting others. 
       </p>
<div class="alert"><b>Note</b>  The NIC must not split IPv6 frames that contain unsupported IPv6 extension
       headers. If an IPv6 frame is split, the header portion of the split frame must contain the entire IPv6
       header and all of the IPv6 extension headers that are present.</div>
<div> </div>
</dd>

### -field <a id="NDIS_HD_SPLIT_CAPS_SUPPORTS_TCP_OPTIONS"></a><a id="ndis_hd_split_caps_supports_tcp_options"></a>NDIS_HD_SPLIT_CAPS_SUPPORTS_TCP_OPTIONS

<dd>
<p>The miniport adapter can split TCP frames with other TCP options in addition to the timestamp
       option. The miniport adapter can support some TCP options and not support others.
       </p>
<div class="alert"><b>Note</b>  If the only TCP option in a frame is the timestamp option, the data-split
       provider must be able to split the frame.</div>
<div> </div>
<div class="alert"><b>Note</b>  If a TCP header contains an unsupported TCP option, the NIC must split the frame
       at the beginning of the TCP header or must not split the frame.</div>
<div> </div>
</dd>
</dl>
</dd>

### -field <b>CurrentCapabilities</b>

<dd>
<p>The current header-data split capabilities that the miniport adapter supports. The miniport driver
     uses the same flags that are defined for the 
     <b>HardwareCapabilities</b> member. In this case, the flags are set to indicate the current capabilities
     that depend on the current configuration settings.</p>
</dd>

### -field <b>HDSplitFlags</b>

<dd>
<p>A set of flags that control the status of header-data split for a miniport adapter. The miniport
     driver should set this member to zero before calling the 
     <a href="https://msdn.microsoft.com/861626af-23ea-40dc-a91a-7da42d4b0a1c">
     NdisMSetMiniportAttributes</a> function. After 
     <b>NdisMSetMiniportAttributes</b> successfully returns, the driver must check the flags and configure the
     hardware accordingly. NDIS sets this member with a bitwise OR of the following flags:
     </p>
<p></p>
<dl>

### -field <a id="NDIS_HD_SPLIT_ENABLE_HEADER_DATA_SPLIT"></a><a id="ndis_hd_split_enable_header_data_split"></a>NDIS_HD_SPLIT_ENABLE_HEADER_DATA_SPLIT

<dd>
<p>If this flag is set, the miniport driver should enable header-data split in the hardware.
       Otherwise, header-data split is disabled. If the computer uses header-data split and the miniport
       driver also set the NDIS_HD_SPLIT_CAPS_SUPPORTS_HEADER_DATA_SPLIT flag in the 
       <b>CurrentCapabilities</b> member, NDIS sets NDIS_HD_SPLIT_ENABLE_HEADER_DATA_SPLIT.</p>
</dd>
</dl>
</dd>

### -field <b>BackfillSize</b>

<dd>
<p>The backfill size, in bytes, for the data portion of a split frame. The miniport driver should set
     
     <b>BackfillSize</b> to zero before calling 
     <b>NdisMSetMiniportAttributes</b>. NDIS sets this member if the miniport driver must pre-allocate
     backfill storage in the data portion for split frames. After 
     <b>NdisMSetMiniportAttributes</b> successfully returns, the driver must use the 
     <b>BackfillSize</b> value that NDIS set to pre-allocate the data buffers.</p>
</dd>

### -field <b>MaxHeaderSize</b>

<dd>
<p>The maximum size, in bytes, for the header portion of a split frame. The miniport driver should
     set 
     <b>MaxHeaderSize</b> to zero before calling 
     <b>NdisMSetMiniportAttributes</b>. NDIS sets this member to the maximum size for the header buffer for
     split frames. After 
     <b>NdisMSetMiniportAttributes</b> successfully returns, the driver must use the value that NDIS provided.
     
     </p>
<div class="alert"><b>Note</b>  If the length of a header exceeds 
     <b>MaxHeaderSize</b> because of the presence of IPv4 options, IPSec headers, or IPv6 extension headers,
     the frame must not be split. If a header that includes a TCP or UDP header exceeds 
     <b>MaxHeaderSize</b> because of the presence of TCP header, TCP options, or UDP header, the NIC must
     split the frame at the beginning of the upper layer protocol header or must not split the
     frame.</div>
<div> </div>
</dd>
</dl>

## -remarks
<p>To support header-data split, a miniport driver passes a pointer to an 
    <a href="https://msdn.microsoft.com/b0662a2c-feb6-4d66-89c9-586c2859b78b">
    NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a> structure in the 
    <i>MiniportAttributes</i> parameter of the 
    <a href="https://msdn.microsoft.com/861626af-23ea-40dc-a91a-7da42d4b0a1c">
    NdisMSetMiniportAttributes</a> function. The 
    <b>HDSplitAttributes</b> member of NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES contains a pointer to
    the NDIS_HD_SPLIT_ATTRIBUTES structure. A miniport driver calls 
    <b>NdisMSetMiniportAttributes</b> from its 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function
    during initialization.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.1 and later.</p>
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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b0662a2c-feb6-4d66-89c9-586c2859b78b">
   NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_HD_SPLIT_ATTRIBUTES structure%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
