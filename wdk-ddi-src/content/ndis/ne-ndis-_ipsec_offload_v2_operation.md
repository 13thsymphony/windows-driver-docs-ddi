---
UID : NE:ndis._IPSEC_OFFLOAD_V2_OPERATION
title : "_IPSEC_OFFLOAD_V2_OPERATION"
author : windows-driver-content
description : The IPSEC_OFFLOAD_V2_OPERATION enumeration specifies the IPsec operation for which a security association (SA) is used.
old-location : netvista\ipsec_offload_v2_operation.htm
old-project : netvista
ms.assetid : bb26c8af-1564-4cf8-ab40-b50b4811466d
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis/IPSEC_OFFLOAD_V2_OPERATION, IPsecOffloadV2Max, task_offload_IPsecv2_ref_37a1424a-fe40-440d-a071-9483c5bcb516.xml, ndis/PIPSEC_OFFLOAD_V2_OPERATION, IPsecOffloadV2Ah, IPsecOffloadV2Esp, netvista.ipsec_offload_v2_operation, ndis/IPsecOffloadV2Esp, ndis/IPsecOffloadV2Ah, IPSEC_OFFLOAD_V2_OPERATION enumeration [Network Drivers Starting with Windows Vista], _IPSEC_OFFLOAD_V2_OPERATION, PIPSEC_OFFLOAD_V2_OPERATION enumeration pointer [Network Drivers Starting with Windows Vista], PIPSEC_OFFLOAD_V2_OPERATION, *PIPSEC_OFFLOAD_V2_OPERATION, IPSEC_OFFLOAD_V2_OPERATION, ndis/IPsecOffloadV2Max
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.1 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : IPSEC_OFFLOAD_V2_OPERATION, *PIPSEC_OFFLOAD_V2_OPERATION
---

# _IPSEC_OFFLOAD_V2_OPERATION Enumeration
<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]

The IPSEC_OFFLOAD_V2_OPERATION enumeration specifies the IPsec operation for which a security
  association (SA) is used.

## Syntax
````
typedef enum _IPSEC_OFFLOAD_V2_OPERATION { 
  IPsecOffloadV2Ah   = 1,
  IPsecOffloadV2Esp,
  IPsecOffloadV2Max
} IPSEC_OFFLOAD_V2_OPERATION, *PIPSEC_OFFLOAD_V2_OPERATION;
````

## Constants

<table>

<tr>
<td>IPsecOffloadV2Ah</td>
<td>The SA is used for authentication (integrity checking).</td>
</tr>

<tr>
<td>IPsecOffloadV2Esp</td>
<td>The SA is used for encryption/decryption (confidentiality).</td>
</tr>

<tr>
<td>IPsecOffloadV2Max</td>
<td>Reserved for NDIS.</td>
</tr>
</table>

## Remarks

The IPSEC_OFFLOAD_V2_OPERATION enumeration specifies the operation for which an SA is used in the 
    <b>Operation</b> member of the 
    <mshelp:link keywords="netvista.ipsec_offload_v2_security_association" tabindex="0"><b>
    IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION</b></mshelp:link> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<mshelp:link keywords="netvista.ipsec_offload_v2_security_association" tabindex="0"><b>
   IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20IPSEC_OFFLOAD_V2_OPERATION enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>