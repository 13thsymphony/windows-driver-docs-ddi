---
UID: NS:ndis._NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO
title: _NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO
author: windows-driver-content
description: The NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO structure specifies IPsec header information in the OOB data of a NET_BUFFER_LIST structure.
old-location: netvista\ndis_ipsec_offload_v2_header_net_buffer_list_info.htm
old-project: netvista
ms.assetid: 657c7941-5475-4351-a429-94003a5c21d9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO, NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO, *PNDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO
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
req.typenames: NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO, *PNDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO
---

# _NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO structure



## -description
<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]

The NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO structure specifies IPsec header information in
  the OOB data of a 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.



## -syntax

````
typedef struct _NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO {
  union {
    struct {
      ULONG NextHeader  :8;
      ULONG PadLength  :8;
      ULONG AhHeaderOffset  :8;
      ULONG EspHeaderOffset  :8;
    } Transmit;
    struct {
      ULONG NextHeader  :8;
      ULONG PadLength  :8;
      ULONG HeaderInfoSet  :1;
    } Receive;
  };
} NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO, *PNDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO;
````


## -struct-fields

### -field Transmit

A structure that contains the following members:


### -field NextHeader

The next header value that is carried in the ESP trailer.


### -field PadLength

The amount of padding, in bytes, that is added to the end of the payload for ESP only. 
       <b>PadLength</b> is specified for IPsec offload packets with and without large send offload (LSO).


### -field AhHeaderOffset

The offset count from the beginning of the IP header to the AH header. The 
       <b>AhHeaderOffset</b> value is this offset, in bytes, divided by 4 to reduce the number of bits that
       are required to represent the offset. Note that the AH header is, at minimum, aligned on 4-byte
       boundaries.


### -field EspHeaderOffset

The offset count from the beginning of the IP header to the ESP header. The 
       <b>EspHeaderOffset</b> value is this offset, in bytes, divided by 4 to reduce the number of bits that
       are required to represent the offset. Note that the ESP header is, at minimum, aligned on 4-byte
       boundaries.

</dd>
</dl>

### -field Receive

A structure that contains the following members:


### -field NextHeader

The next header value that is carried in the ESP trailer.


### -field PadLength

The amount of padding, in bytes, that is added to the end of the payload for ESP only. 
       <b>PadLength</b> is specified for IPsec offload packets with and without large send offload (LSO).


### -field HeaderInfoSet

A ULONG value that, when set, indicates the members of the 
       <b>Receive</b> structure are valid. If this member is not set, the 
       <b>Receive</b> structure is ignored.

</dd>
</dl>

## -remarks
The information in the NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO structure makes it easy for
    the miniport driver to parse an outbound packet. NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO
    specifies the header offsets for IPsec headers in the 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure as well as the
    location of the next header and the padding length.

To set and get the IPsec tunnel information, use the 
    <b>IPsecOffloadV2HeaderNetBufferListInfo</b> index with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro.
    NET_BUFFER_LIST_INFO returns an NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO structure.


## -see-also
<dl>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

