---
UID: NS:ntddndis._NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS
title: "_NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS"
author: windows-driver-content
description: The NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS structure specifies the information about the network adapter switch that will be deleted from the network adapter.
old-location: netvista\ndis_nic_switch_delete_switch_parameters.htm
old-project: netvista
ms.assetid: 859D6DA7-5945-44FA-8DDC-99EBD97883D2
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS, NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS, NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS, PNDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS, netvista.ndis_nic_switch_delete_switch_parameters, ntddndis/NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS, ntddndis/PNDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
-	Ntddndis.h
api_name:
-	NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS, *PNDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS
---

# _NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS structure
The <b>NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS</b> structure specifies the information about the network adapter switch that will be deleted from the network adapter.

## Syntax
```
typedef struct _NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  NDIS_NIC_SWITCH_ID SwitchId;
} *PNDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS, NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS;
```

## Members


`Header`

The type, revision, and size of the <b>NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value. 





#### NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS_REVISION_1

Original version for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_PARAMETERS_REVISION_1.

`Flags`

A ULONG value that contains a bitwise OR of flags. This member is reserved for NDIS.

`SwitchId`

An NDIS_NIC_SWITCH_ID value that specifies a switch identifier. The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch.



<div class="alert"><b>Note</b>  Starting with Windows Server 2012, SR-IOV only supports the default network adapter switch on the network adapter. This member must be set to NDIS_DEFAULT_SWITCH_ID. </div>
<div> </div>

## Remarks
The <b>NDIS_NIC_SWITCH_DELETE_SWITCH_PARAMETERS</b> structure is used in OID method requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451817">OID_NIC_SWITCH_DELETE_SWITCH</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later. Supported in NDIS 6.30 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451817">OID_NIC_SWITCH_DELETE_SWITCH</a>