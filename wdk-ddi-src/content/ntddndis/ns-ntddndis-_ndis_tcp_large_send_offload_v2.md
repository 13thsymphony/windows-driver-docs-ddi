---
UID : NS:ntddndis._NDIS_TCP_LARGE_SEND_OFFLOAD_V2
title : _NDIS_TCP_LARGE_SEND_OFFLOAD_V2
author : windows-driver-content
description : The NDIS_TCP_LARGE_SEND_OFFLOAD_V2 structure provides large send offload version 2 (LSOV2) information in the NDIS_OFFLOAD structure.
old-location : netvista\ndis_tcp_large_send_offload_v2.htm
old-project : netvista
ms.assetid : e53e5771-a3ca-4867-a0ac-65adb66e574c
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _NDIS_TCP_LARGE_SEND_OFFLOAD_V2, *PNDIS_TCP_LARGE_SEND_OFFLOAD_V2, NDIS_TCP_LARGE_SEND_OFFLOAD_V2
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NDIS_TCP_LARGE_SEND_OFFLOAD_V2
req.alt-loc : ntddndis.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : "*PNDIS_TCP_LARGE_SEND_OFFLOAD_V2, NDIS_TCP_LARGE_SEND_OFFLOAD_V2"
---

# _NDIS_TCP_LARGE_SEND_OFFLOAD_V2 structure
The <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V2</b> structure provides large send offload version 2 (LSOV2)
  information in the 
  <a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> structure.

## Syntax
````
typedef struct _NDIS_TCP_LARGE_SEND_OFFLOAD_V2 {
  struct {
    ULONG Encapsulation;
    ULONG MaxOffLoadSize;
    ULONG MinSegmentCount;
  } IPv4;
  struct {
    ULONG Encapsulation;
    ULONG MaxOffLoadSize;
    ULONG MinSegmentCount;
    ULONG IpExtensionHeadersSupported  :2;
    ULONG TcpOptionsSupported  :2;
  } IPv6;
} NDIS_TCP_LARGE_SEND_OFFLOAD_V2, *PNDIS_TCP_LARGE_SEND_OFFLOAD_V2;
````

## Members

        
            `IPv4`

            A structure within <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V2</b> that specifies IPv4 information and that
     contains the following members:
        
            `IPv6`

            A structure within <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V2</b> that specifies IPv6 information and that
     contains the following members:

    ## Remarks
        The <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V2</b> structure is used in the 
    <b>LsoV2</b> member of the 
    <a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> structure. The
    <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V2</b> structure specifies current or supported services that a miniport adapter
    provides for segmenting large TCP packets into smaller packets. NDIS also provides large send offload
    version 1 (LSOV1), which is an earlier version of LSOV2. For more information about LSOV1, see 
    <a href="..\ntddndis\ns-ntddndis-_ndis_tcp_large_send_offload_v1.md">
    NDIS_TCP_LARGE_SEND_OFFLOAD_V1</a>.


<a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> is used in the 
    <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_offload_attributes.md">
    NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a> structure, 
    <a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a> structure, 
    <a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">
    NDIS_FILTER_ATTACH_PARAMETERS</a> structure, 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">
    OID_TCP_OFFLOAD_CURRENT_CONFIG</a> OID, and the 
    <a href="netvista.ndis_status_task_offload_current_config">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication.

For 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>,
    the <a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> structure specifies the task offload capabilities that a miniport adapter supports. If
    the current offloads capabilities change, a miniport driver reports the new capabilities in an 
    <a href="netvista.ndis_status_task_offload_current_config">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication.

The 
    <b>Encapsulation</b> members of <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V2</b> define the LSOV2 encapsulation settings for
    the miniport adapter.

In response to an 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">
    OID_TCP_OFFLOAD_CURRENT_CONFIG</a> query request, NDIS provides a bitwise OR of the encapsulation
    flags, which indicate the supported encapsulation settings, in each of the 
    <b>Encapsulation</b> members. Miniport drivers must provide Ethernet encapsulation
    (NDIS_ENCAPSULATION_IEEE_802_3). The other types of encapsulation are optional.

For an 
    <a href="netvista.ndis_status_task_offload_current_config">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication, the miniport driver provides a bitwise
    OR of the encapsulation flags, which indicate the current capabilities, in each of the 
    <b>Encapsulation</b> members.

The following flags are defined for the 
    <b>Encapsulation</b> members:



Specifies that no encapsulation offload is supported.

Specifies NULL encapsulation.

Specifies IEEE 802.3 encapsulation.

Specifies IEEE 802.3p and IEEE 802.3q encapsulation.

Specifies that IEEE 802.3p and IEEE 802.3q encapsulation settings are specified in the 
      <b>NetBufferListInfo</b> member of each 
      <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

Specifies logical link control (LLC) encapsulation for routed protocols, as described in RFC
      1483. This flag is also used to indicate Ethernet LLC/SNAP encapsulation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddndis.h (include Ndis.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">NDIS_FILTER_ATTACH_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_offload_attributes.md">
   NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="netvista.ndis_status_task_offload_current_config">
   NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_tcp_large_send_offload_v1.md">
   NDIS_TCP_LARGE_SEND_OFFLOAD_V1</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_TCP_LARGE_SEND_OFFLOAD_V2 structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>