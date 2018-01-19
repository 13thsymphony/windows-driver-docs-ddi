---
UID : NS:ntddndis._NDIS_RECEIVE_HASH_PARAMETERS
title : _NDIS_RECEIVE_HASH_PARAMETERS
author : windows-driver-content
description : The NDIS_RECEIVE_HASH_PARAMETERS structure specifies the receive hash parameters for a miniport adapter that supports receive hash calculations.
old-location : netvista\ndis_receive_hash_parameters.htm
old-project : netvista
ms.assetid : 02c333d3-9ea7-4d24-9e09-32943c00d6a5
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _NDIS_RECEIVE_HASH_PARAMETERS, NDIS_RECEIVE_HASH_PARAMETERS, *PNDIS_RECEIVE_HASH_PARAMETERS
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
req.alt-api : NDIS_RECEIVE_HASH_PARAMETERS
req.alt-loc : Ntddndis.h
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
req.typenames : NDIS_RECEIVE_HASH_PARAMETERS, *PNDIS_RECEIVE_HASH_PARAMETERS
---

# _NDIS_RECEIVE_HASH_PARAMETERS structure
The NDIS_RECEIVE_HASH_PARAMETERS structure specifies the receive hash parameters for a miniport
  adapter that supports receive hash calculations.

## Syntax
````
typedef struct _NDIS_RECEIVE_HASH_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  ULONG              HashInformation;
  USHORT             HashSecretKeySize;
  ULONG              HashSecretKeyOffset;
} NDIS_RECEIVE_HASH_PARAMETERS, *PNDIS_RECEIVE_HASH_PARAMETERS;
````

## Members

        
            `Flags`

            A USHORT value that indicates what the miniport driver should do with the hash parameters. The
     miniport driver can use these flags to quickly determine which parameters have changed and update the
     hash settings accordingly. 
     

In a set request, the flags are defined as follows:
        
            `HashInformation`

            In a set request, the hash type and hash function that the NIC should use to compute the hash
     values for the incoming packets.
     

In a query request, the hash type and hash function that the NIC is using.

Overlying drivers and NDIS can use the 
     <a href="netvista.ndis_rss_hash_info_from_type_and_func">
     NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC</a> macro to combine the hash type and hash function into hash
     information and set the 
     <b>HashInformation</b> member.

Miniport drivers can use the 
     <a href="netvista.ndis_rss_hash_type_from_hash_info">
     NDIS_RSS_HASH_TYPE_FROM_HASH_INFO</a> macro to get the hash type from 
     <b>HashInformation</b> and the 
     <a href="netvista.ndis_rss_hash_func_from_hash_info">
     NDIS_RSS_HASH_FUNC_FROM_HASH_INFO</a> macro to get the hash function.
        
            `HashSecretKeyOffset`

            The offset of the secret key array of the hash function from the beginning of the
     NDIS_RECEIVE_HASH_PARAMETERS structure. Use this offset to get the 320-bit (40 bytes) secret key. 
     

In a set request, the secret key can contain any data that the overlying driver chooses.

In a query request, the secret key contains the data that the NIC is using.
        
            `HashSecretKeySize`

            The size of the secret key array of the hash function, in bytes. The size of the array is 40 bytes for NdisHashFunctionToeplitz.
        
            `Header`

            The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_RECEIVE_HASH_PARAMETERS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_RECEIVE_HASH_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_RECEIVE_HASH_PARAMETERS_REVISION_1.

    ## Remarks
        The NDIS_RECEIVE_HASH_PARAMETERS structure defines the hash parameters for the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569635">OID_GEN_RECEIVE_HASH</a> OID.

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
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndis_rss_hash_info_from_type_and_func">
   NDIS_RSS_HASH_INFO_FROM_TYPE_AND_FUNC</a>
</dt>
<dt>
<a href="netvista.ndis_rss_hash_func_from_hash_info">
   NDIS_RSS_HASH_FUNC_FROM_HASH_INFO</a>
</dt>
<dt>
<a href="netvista.ndis_rss_hash_type_from_hash_info">
   NDIS_RSS_HASH_TYPE_FROM_HASH_INFO</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569635">OID_GEN_RECEIVE_HASH</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_HASH_PARAMETERS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>