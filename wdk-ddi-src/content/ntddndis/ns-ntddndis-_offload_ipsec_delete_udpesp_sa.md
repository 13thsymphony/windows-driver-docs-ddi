---
UID : NS:ntddndis._OFFLOAD_IPSEC_DELETE_UDPESP_SA
title : "_OFFLOAD_IPSEC_DELETE_UDPESP_SA"
author : windows-driver-content
description : The OFFLOAD_IPSEC_DELETE_UDPESP_SA structure contains information for each security association (SA) and parser entry that a miniport driver deletes from a NIC.
old-location : netvista\offload_ipsec_delete_udpesp_sa.htm
old-project : netvista
ms.assetid : f1304fb4-87c8-4a0f-a10f-6a2c5cbaed20
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : 216offload_7d48a18d-546e-4e72-baf6-5a9e8de5a615.xml, _OFFLOAD_IPSEC_DELETE_UDPESP_SA, *POFFLOAD_IPSEC_DELETE_UDPESP_SA, ntddndis/OFFLOAD_IPSEC_DELETE_UDPESP_SA, POFFLOAD_IPSEC_DELETE_UDPESP_SA structure pointer [Network Drivers Starting with Windows Vista], POFFLOAD_IPSEC_DELETE_UDPESP_SA, netvista.offload_ipsec_delete_udpesp_sa, OFFLOAD_IPSEC_DELETE_UDPESP_SA, OFFLOAD_IPSEC_DELETE_UDPESP_SA structure [Network Drivers Starting with Windows Vista], ntddndis/POFFLOAD_IPSEC_DELETE_UDPESP_SA
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
req.typenames : OFFLOAD_IPSEC_DELETE_UDPESP_SA, *POFFLOAD_IPSEC_DELETE_UDPESP_SA
---

# _OFFLOAD_IPSEC_DELETE_UDPESP_SA structure
The OFFLOAD_IPSEC_DELETE_UDPESP_SA structure contains information for each security association (SA)
  and parser entry that a miniport driver deletes from a NIC.

## Syntax
````
typedef struct _OFFLOAD_IPSEC_DELETE_UDPESP_SA {
  HANDLE OffloadHandle;
  HANDLE EncapTypeEntryOffldHandle;
} OFFLOAD_IPSEC_DELETE_UDPESP_SA, *POFFLOAD_IPSEC_DELETE_UDPESP_SA;
````

## Members


`EncapTypeEntryOffldHandle`

When <b>NULL</b>, the miniport does not have to delete a parser entry in addition to the specified SA.
     When non-<b>NULL</b>, this member specifies the handle for the parser entry to be deleted.

`OffloadHandle`

The handle for the SA to be deleted.

## Remarks
The OFFLOAD_IPSEC_DELETE_UDPESP_SA structure is used with the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff569809">
    OID_TCP_TASK_IPSEC_DELETE_UDPESP_SA</a> OID.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff569809">
   OID_TCP_TASK_IPSEC_DELETE_UDPESP_SA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20OFFLOAD_IPSEC_DELETE_UDPESP_SA structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>