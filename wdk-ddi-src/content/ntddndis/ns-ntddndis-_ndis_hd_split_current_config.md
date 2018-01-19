---
UID : NS:ntddndis._NDIS_HD_SPLIT_CURRENT_CONFIG
title : _NDIS_HD_SPLIT_CURRENT_CONFIG
author : windows-driver-content
description : The NDIS_HD_SPLIT_CURRENT_CONFIG structure provides the current header-data split configuration of a miniport adapter.
old-location : netvista\ndis_hd_split_current_config.htm
old-project : netvista
ms.assetid : 866fe9e6-0cb1-45cd-84b4-4e2df9c9c45a
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _NDIS_HD_SPLIT_CURRENT_CONFIG, NDIS_HD_SPLIT_CURRENT_CONFIG, *PNDIS_HD_SPLIT_CURRENT_CONFIG
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.1 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NDIS_HD_SPLIT_CURRENT_CONFIG
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
req.typenames : NDIS_HD_SPLIT_CURRENT_CONFIG, *PNDIS_HD_SPLIT_CURRENT_CONFIG
---

# _NDIS_HD_SPLIT_CURRENT_CONFIG structure
The NDIS_HD_SPLIT_CURRENT_CONFIG structure provides the current header-data split configuration of a
  miniport adapter.

## Syntax
````
typedef struct _NDIS_HD_SPLIT_CURRENT_CONFIG {
  NDIS_OBJECT_HEADER Header;
  ULONG              HardwareCapabilities;
  ULONG              CurrentCapabilities;
  ULONG              HDSplitFlags;
  ULONG              HDSplitCombineFlags;
  ULONG              BackfillSize;
  ULONG              MaxHeaderSize;
} NDIS_HD_SPLIT_CURRENT_CONFIG, *PNDIS_HD_SPLIT_CURRENT_CONFIG;
````

## Members

        
            `BackfillSize`

            The backfill size, in bytes, that the miniport driver is using for the data portion of a split
     frame.
        
            `CurrentCapabilities`

            The current header-data split capabilities that the miniport adapter supports. The miniport driver
     uses the same flags that are defined for the 
     <b>HardwareCapabilities</b> member. In this case, the flags are set to indicate the current capabilities
     that depend on the current configuration settings.
        
            `HardwareCapabilities`

            The header-data split hardware capabilities that the miniport adapter supports. These capabilities
     should include capabilities that are currently disabled by INF file settings or through the 
     <b>Advanced</b> properties page. The value of 
     <b>HardwareCapabilities</b> is a bitwise OR of the following flags:
        
            `HDSplitCombineFlags`

            A set of flags that specify the current header-data split settings of a miniport adapter. The
     value of 
     <b>HDSplitCombineFlags</b> can be a bitwise OR of the following flags:
        
            `HDSplitFlags`

            A set of flags that reports the status of header-data split for a miniport adapter. NDIS sets this
     member with a bitwise OR of the following flags:
        
            `Header`

            The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_HD_SPLIT_CURRENT_CONFIG structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_HD_SPLIT_CURRENT_CONFIG_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_HD_SPLIT_CURRENT_CONFIG_REVISION_1.
        
            `MaxHeaderSize`

            The maximum size, in bytes, that the miniport driver is using for the header portion of a split
     frame. 
     

<div class="alert"><b>Note</b>  If the length of a header exceeds 
     <b>MaxHeaderSize</b> because of the presence of IPv4 options, IPsec headers, or IPv6 extension headers,
     the frame must not be split. If a header that includes a TCP or UDP header exceeds 
     <b>MaxHeaderSize</b> because of the presence of TCP header, TCP options, or UDP header, the NIC must
     split the frame at the beginning of the upper layer protocol header or must not split the
     frame.</div>
<div> </div>

    ## Remarks
        The NDIS_HD_SPLIT_CURRENT_CONFIG structure is used in the 
    <a href="netvista.oid_gen_hd_split_current_config">
    OID_GEN_HD_SPLIT_CURRENT_CONFIG</a> OID query request to obtain the current header-data split
    configuration of a miniport adapter.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569586">OID_GEN_HD_SPLIT_CURRENT_CONFIG</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_HD_SPLIT_CURRENT_CONFIG structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>