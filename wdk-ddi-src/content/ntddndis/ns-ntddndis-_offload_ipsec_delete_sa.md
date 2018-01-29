---
UID : NS:ntddndis._OFFLOAD_IPSEC_DELETE_SA
title : _OFFLOAD_IPSEC_DELETE_SA
author : windows-driver-content
description : The OFFLOAD_IPSEC_DELETE_SA structure contains information for each security association (SA) that a miniport driver deletes from a NIC.
old-location : netvista\offload_ipsec_delete_sa.htm
old-project : netvista
ms.assetid : a8c34bf8-1f3a-4aa3-834b-5824402bd88c
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : OFFLOAD_IPSEC_DELETE_SA, ntddndis/POFFLOAD_IPSEC_DELETE_SA, 216offload_1e6bbc64-755a-4da3-a7d2-ce57c4b98ce6.xml, _OFFLOAD_IPSEC_DELETE_SA, POFFLOAD_IPSEC_DELETE_SA, ntddndis/OFFLOAD_IPSEC_DELETE_SA, OFFLOAD_IPSEC_DELETE_SA structure [Network Drivers Starting with Windows Vista], *POFFLOAD_IPSEC_DELETE_SA, netvista.offload_ipsec_delete_sa, POFFLOAD_IPSEC_DELETE_SA structure pointer [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : 
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
req.typenames : OFFLOAD_IPSEC_DELETE_SA, *POFFLOAD_IPSEC_DELETE_SA
---

# _OFFLOAD_IPSEC_DELETE_SA structure
The OFFLOAD_IPSEC_DELETE_SA structure contains information for each security association (SA) that a
  miniport driver deletes from a NIC.

## Syntax
````
typedef struct _OFFLOAD_IPSEC_DELETE_SA {
  HANDLE OffloadHandle;
} OFFLOAD_IPSEC_DELETE_SA, *POFFLOAD_IPSEC_DELETE_SA;
````

## Members


`OffloadHandle`

The handle for the SA to be deleted.

## Remarks
The OFFLOAD_IPSEC_DELETE_SA structure is used with the 
    <mshelp:link keywords="netvista.oid_tcp_task_ipsec_delete_sa" tabindex="0">
    OID_TCP_TASK_IPSEC_DELETE_SA</mshelp:link> OID.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/gg155485.aspx">OID_TCP_TASK_IPSEC_DELETE_SA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20OFFLOAD_IPSEC_DELETE_SA structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>