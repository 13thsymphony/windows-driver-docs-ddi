---
UID : NS:ntddndis._NDIS_NIC_SWITCH_PARAMETERS
title : "_NDIS_NIC_SWITCH_PARAMETERS"
author : windows-driver-content
description : The NDIS_NIC_SWITCH_PARAMETERS structure specifies the configuration parameters of a network adapter switch on the network adapter.
old-location : netvista\ndis_nic_switch_parameters.htm
old-project : netvista
ms.assetid : BC43A7DF-51B4-4571-86C5-12B332B13084
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : PNDIS_NIC_SWITCH_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], *PNDIS_NIC_SWITCH_PARAMETERS, _NDIS_NIC_SWITCH_PARAMETERS, NDIS_NIC_SWITCH_PARAMETERS, ntddndis/NDIS_NIC_SWITCH_PARAMETERS, NDIS_NIC_SWITCH_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_NIC_SWITCH_PARAMETERS, netvista.ndis_nic_switch_parameters, ntddndis/PNDIS_NIC_SWITCH_PARAMETERS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.30 and later.
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
req.typenames : "*PNDIS_NIC_SWITCH_PARAMETERS, NDIS_NIC_SWITCH_PARAMETERS"
---

# _NDIS_NIC_SWITCH_PARAMETERS structure
The <b>NDIS_NIC_SWITCH_PARAMETERS</b> structure specifies the configuration parameters of a network adapter switch on the network adapter.

## Syntax
````
typedef struct _NDIS_NIC_SWITCH_PARAMETERS {
  NDIS_OBJECT_HEADER            Header;
  ULONG                         Flags;
  NDIS_NIC_SWITCH_TYPE          SwitchType;
  NDIS_NIC_SWITCH_ID            SwitchId;
  NDIS_NIC_SWITCH_FRIENDLY_NAME SwitchFriendlyName;
  ULONG                         NumVFs;
  ULONG                         NdisReserved1;
  ULONG                         NdisReserved2;
  ULONG                         NdisReserved3;
} NDIS_NIC_SWITCH_PARAMETERS, *PNDIS_NIC_SWITCH_PARAMETERS;
````

## Members


`Flags`

A ULONG value that contains a bitwise OR of flags. The following flags are defined for this member. 





#### NDIS_NIC_SWITCH_PARAMETERS_SWITCH_NAME_CHANGED

This flag specifies that the field that has been updated in the <b>NDIS_NIC_SWITCH_PARAMETERS</b> structure is the <b>SwitchName</b> member.
<div class="alert"><b>Note</b>  This flag is valid only when this structure is used in an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451823">OID_NIC_SWITCH_PARAMETERS</a>. </div><div> </div>

`Header`

The type, revision, and size of the <b>NDIS_NIC_SWITCH_PARAMETERS</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 




#### NDIS_NIC_SWITCH_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_PARAMETERS_REVISION_1.

`NdisReserved1`

Reserved for NDIS.

`NdisReserved2`

Reserved for NDIS.

`NdisReserved3`

Reserved for NDIS.

`NumQueuePairsForDefaultVPort`



`NumVFs`

A ULONG value that specifies the number of PCI Express (PCIe) Virtual Functions (VFs) that are enabled on the network adapter. VFs are enabled on the adapter when virtualization is enabled through a call to <a href="..\ndis\nf-ndis-ndismenablevirtualization.md">NdisMEnableVirtualization</a>.
<div class="alert"><b>Note</b>  Before a VF can be attached to a Hyper-V child partition, resources must be allocated for it through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>.</div><div> </div>

`SwitchFriendlyName`

An NDIS_NIC_SWITCH_FRIENDLY_NAME value that contains a description for the switch.

`SwitchId`

An NDIS_NIC_SWITCH_ID value that contains a switch identifier. The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch.


<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the single root I/O virtualization (SR-IOV) interface only supports the default network adapter switch on the network adapter. The value of this member must be set to NDIS_DEFAULT_SWITCH_ID. </div><div> </div>

`SwitchType`

An 
     <a href="..\ntddndis\ne-ntddndis-_ndis_nic_switch_type.md">NDIS_NIC_SWITCH_TYPE</a> enumeration value that
     specifies the type of the network adapter switch.
<div class="alert"><b>Note</b>   Starting with Windows Server 2012, Windows only supports a switch type of <b>NdisNicSwitchTypeExternal</b>.  An external switch specifies that the ports connected to this type of switch can access the external network through the physical port on the network adapter. The default virtual port (VPort) on the external switch provides external network connectivity to the virtualization stack that runs in the management operating system of the Hyper-V parent partition.</div><div> </div>

## Remarks
The <b>NDIS_NIC_SWITCH_PARAMETERS</b> structure is used in OID method requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451815">OID_NIC_SWITCH_CREATE_SWITCH</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh451823">OID_NIC_SWITCH_PARAMETERS</a>. These OID requests set or query the configuration parameters of a network adapter switch. 

For more information about the SR-IOV interface, see 	<a href="https://msdn.microsoft.com/B241F468-F568-4500-9356-E576CEBA8F3B">Overview of Single Root I/O Virtualization (SR-IOV)</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ndis\nf-ndis-ndismenablevirtualization.md">NdisMEnableVirtualization</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451823">OID_NIC_SWITCH_PARAMETERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451815">OID_NIC_SWITCH_CREATE_SWITCH</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<b></b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NIC_SWITCH_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>