---
UID: NS:ntddndis._NDIS_SRIOV_PF_LUID_INFO
title: "_NDIS_SRIOV_PF_LUID_INFO"
author: windows-driver-content
description: The NDIS_SRIOV_PF_LUID_INFO structure specifies the locally unique identifier (LUID) associated with the network adapter's PCI Express (PCIe) Physical Function (PF).
old-location: netvista\ndis_sriov_pf_luid_info.htm
old-project: netvista
ms.assetid: 03a83321-8396-4400-a15c-84a3b507702d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_SRIOV_PF_LUID_INFO, NDIS_SRIOV_PF_LUID_INFO, NDIS_SRIOV_PF_LUID_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_SRIOV_PF_LUID_INFO, PNDIS_SRIOV_PF_LUID_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SRIOV_PF_LUID_INFO, netvista.ndis_sriov_pf_luid_info, ntddndis/NDIS_SRIOV_PF_LUID_INFO, ntddndis/PNDIS_SRIOV_PF_LUID_INFO"
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
-	NDIS_SRIOV_PF_LUID_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_SRIOV_PF_LUID_INFO, *PNDIS_SRIOV_PF_LUID_INFO
---

# _NDIS_SRIOV_PF_LUID_INFO structure
The <b>NDIS_SRIOV_PF_LUID_INFO</b> structure specifies the locally unique identifier (LUID) associated with the network adapter's PCI Express (PCIe) Physical Function (PF).

## Syntax
````
typedef struct _NDIS_SRIOV_PF_LUID_INFO {
  NDIS_OBJECT_HEADER Header;
  LUID               Luid;
} NDIS_SRIOV_PF_LUID_INFO, *PNDIS_SRIOV_PF_LUID_INFO;
````

## Members


`Header`

The type, revision, and size of the <b>NDIS_SRIOV_PF_LUID_INFO</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_PF_LUID_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_SRIOV_PF_LUID_INFO_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_PF_LUID_INFO_REVISION_1.

`Luid`

An <a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a> value that is associated with the PF network adapter. For more information, see the Remarks section.

## Remarks
NDIS generates an LUID for the PF  before NDIS calls the <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
 function of the miniport driver for the PF. This LUID is valid until NDIS calls the PF miniport driver's <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function.

<div class="alert"><b>Note</b>  The value of the <b>Luid</b> member is different from the <b>NetLuid</b> member of the <a href="..\ndis\ns-ndis-_ndis_miniport_init_parameters.md">NDIS_MINIPORT_INIT_PARAMETERS</a>  structure. This structure is passed to the miniport driver through the <i>MiniportInitParameters</i> of <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>.</div>
<div> </div>
An overlying driver queries this LUID through OID query requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451864">OID_SRIOV_PF_LUID</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later. Supported in NDIS 6.30 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ndis\ns-ndis-_ndis_miniport_init_parameters.md">NDIS_MINIPORT_INIT_PARAMETERS</a>



<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451864">OID_SRIOV_PF_LUID</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SRIOV_PF_LUID_INFO structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>