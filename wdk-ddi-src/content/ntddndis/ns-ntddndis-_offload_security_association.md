---
UID: NS:ntddndis._OFFLOAD_SECURITY_ASSOCIATION
title: "_OFFLOAD_SECURITY_ASSOCIATION"
author: windows-driver-content
description: The OFFLOAD_SECURITY_ASSOCIATION structure specifies a single security association (SA).
old-location: netvista\offload_security_association.htm
old-project: netvista
ms.assetid: 2c392a13-4db4-4b22-aacf-4450eb1e191c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*POFFLOAD_SECURITY_ASSOCIATION, 216offload_3c6a958b-81b2-4f18-b974-b0669b6294e1.xml, OFFLOAD_SECURITY_ASSOCIATION, OFFLOAD_SECURITY_ASSOCIATION structure [Network Drivers Starting with Windows Vista], POFFLOAD_SECURITY_ASSOCIATION, POFFLOAD_SECURITY_ASSOCIATION structure pointer [Network Drivers Starting with Windows Vista], _OFFLOAD_SECURITY_ASSOCIATION, netvista.offload_security_association, ntddndis/OFFLOAD_SECURITY_ASSOCIATION, ntddndis/POFFLOAD_SECURITY_ASSOCIATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddndis.h
api_name:
-	OFFLOAD_SECURITY_ASSOCIATION
product: Windows
targetos: Windows
req.typenames: OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION
---

# _OFFLOAD_SECURITY_ASSOCIATION structure
The OFFLOAD_SECURITY_ASSOCIATION structure specifies a single security association (SA).

## Syntax
````
typedef struct _OFFLOAD_SECURITY_ASSOCIATION {
  OFFLOAD_OPERATION_E Operation;
  SPI_TYPE            SPI;
  OFFLOAD_ALGO_INFO   IntegrityAlgo;
  OFFLOAD_ALGO_INFO   ConfAlgo;
  OFFLOAD_ALGO_INFO   Reserved;
} OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION;
````

## Members


`ConfAlgo`

The confidentiality (encryption/decryption) algorithm for the SA, formatted as an
     OFFLOAD_ALGO_INFO structure.

`IntegrityAlgo`

The integrity (authentication) algorithm for the SA, formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_offload_algo_info.md">OFFLOAD_ALGO_INFO</a> structure.

`Operation`

The Internet Protocol security (IPsec) operation for which the SA is to be used. The following
     operations are supported:
     





#### AUTHENTICATE

The SA will be used for authentication (integrity checking).



#### ENCRYPT

The SA will be used for encryption/decryption (confidentiality).

`Reserved`

This member is reserved.

`SPI`

The Security Parameters Index (SPI) for the SA.

## Remarks
The OFFLOAD_SECURITY_ASSOCIATION structure is used with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569808">OID_TCP_TASK_IPSEC_ADD_SA</a> and 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-add-udpesp-sa">
    OID_TCP_TASK_IPSEC_ADD_UDPESP_SA</a> OIDs.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_offload_algo_info.md">OFFLOAD_ALGO_INFO</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-add-udpesp-sa">
   OID_TCP_TASK_IPSEC_ADD_UDPESP_SA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569808">OID_TCP_TASK_IPSEC_ADD_SA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20OFFLOAD_SECURITY_ASSOCIATION structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>