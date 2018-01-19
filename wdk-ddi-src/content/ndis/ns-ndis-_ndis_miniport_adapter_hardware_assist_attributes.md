---
UID : NS:ndis._NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES
title : _NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES
author : windows-driver-content
description : The NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES structure specifies the hardware-assisted attributes of the network adapter.
old-location : netvista\ndis_miniport_adapter_hardware_assist_attributes.htm
old-project : netvista
ms.assetid : b0662a2c-feb6-4d66-89c9-586c2859b78b
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES
req.alt-loc : ndis.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : See Remarks section
req.typenames : "*PNDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES"
---

# _NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES structure
The <b>NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</b> structure specifies the hardware-assisted attributes of the network adapter.

## Syntax
````
typedef struct _NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES {
  NDIS_OBJECT_HEADER                Header;
  PNDIS_HD_SPLIT_ATTRIBUTES         HDSplitAttributes;
#if (NDIS_SUPPORT_NDIS620)
  PNDIS_RECEIVE_FILTER_CAPABILITIES HardwareReceiveFilterCapabilities;
  PNDIS_RECEIVE_FILTER_CAPABILITIES CurrentReceiveFilterCapabilities;
  PNDIS_NIC_SWITCH_CAPABILITIES     HardwareNicSwitchCapabilities;
  PNDIS_NIC_SWITCH_CAPABILITIES     CurrentNicSwitchCapabilities;
#endif 
#if NDIS_SUPPORT_NDIS630
  PNDIS_SRIOV_CAPABILITIES          HardwareSriovCapabilities;
  PNDIS_SRIOV_CAPABILITIES          CurrentSriovCapabilities;
  PNDIS_QOS_CAPABILITIES            HardwareQosCapabilities;
  PNDIS_QOS_CAPABILITIES            CurrentQosCapabilities;
#endif 
} NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES;
````

## Members

        
            `CurrentNicSwitchCapabilities`

            A pointer to an <a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_capabilities.md">NDIS_NIC_SWITCH_CAPABILITIES</a> structure. This structure specifies the NIC switch
     capabilities that are currently enabled on the network adapter. This value can be <b>NULL</b> if the network adapter does not support NIC switch features or receive filtering.

<div class="alert"><b>Warning</b>  If this member is not set to NULL, the <b>HardwareNicSwitchCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>
        
            `CurrentQosCapabilities`

            A pointer to an <a href="..\ntddndis\ns-ntddndis-_ndis_qos_capabilities.md">NDIS_QOS_CAPABILITIES</a> structure. This structure specifies the hardware capabilities that are currently enabled on the network adapter for NDIS QoS over the DCB interface. This value can be <b>NULL</b> if the network adapter does not support NDIS QoS hardware capabilities for DCB. 

If the adapter supports NDIS QoS capabilties but those capabilities are disabled, the miniport driver must set all members of the <a href="..\ntddndis\ns-ntddndis-_ndis_qos_capabilities.md">NDIS_QOS_CAPABILITIES</a> structure (with the exception of the <b>Header</b> member) to zero.

<div class="alert"><b>Note</b>  If this member is not set to NULL, the <b>HardwareQosCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>
        
            `CurrentReceiveFilterCapabilities`

            A pointer to an NDIS_RECEIVE_FILTER_CAPABILITIES structure. This structure specifies the receive
     filtering capabilities that are currently enabled on the network adapter. This value can be <b>NULL</b> if the
     network adapter does not support receive filtering.

<div class="alert"><b>Warning</b>  If this member is not set to NULL, the <b>HardwareReceiveFilterCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>
        
            `CurrentSriovCapabilities`

            A pointer to an <a href="..\ntddndis\ns-ntddndis-_ndis_sriov_capabilities.md">NDIS_SRIOV_CAPABILITIES</a> structure. This structure specifies the SR-IOV capabilities that are currently enabled on the network adapter. This value can be <b>NULL</b> if the network adapter does not support SR-IOV. 

<div class="alert"><b>Note</b>  If this member is not set to NULL, the <b>HardwareSriovCapabilities</b>, <b>HardwareNicSwitchCapabilities</b>, and <b>CurrentNicSwitchCapabilities</b> members must not be set to <b>NULL</b>.</div>
<div> </div>
        
            `HardwareNicSwitchCapabilities`

            A pointer to an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_capabilities.md">
     NDIS_NIC_SWITCH_CAPABILITIES</a> structure. This structure specifies the hardware NIC switch
     capabilities of the network adapter. This value can be <b>NULL</b> if the network adapter does not support
     NIC switch features or receive filtering.

<div class="alert"><b>Warning</b>  If this member is not set to NULL, the <b>CurrentNicSwitchCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>
        
            `HardwareQosCapabilities`

            A pointer to an <a href="..\ntddndis\ns-ntddndis-_ndis_qos_capabilities.md">NDIS_QOS_CAPABILITIES</a> structure. This structure specifies the hardware capabilities that the network adapter supports for NDIS quality of service (QoS) over the IEEE 802.1 Data Center Bridging (DCB) interface. This value can be <b>NULL</b> if the network adapter does not support NDIS QoS hardware capabilities for DCB. 

For more information, see <a href="https://msdn.microsoft.com/777988E8-D45E-49A7-B607-5E1218B27B54">NDIS QoS for Data Center Bridging</a>.

<div class="alert"><b>Note</b>  If this member is not set to NULL, the <b>CurrentQosCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>
        
            `HardwareReceiveFilterCapabilities`

            A pointer to an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_receive_filter_capabilities.md">
     NDIS_RECEIVE_FILTER_CAPABILITIES</a> structure. This structure specifies the hardware receive
     filtering capabilities of the network adapter. This value can be <b>NULL</b> if the network adapter does not
     support receive filtering.

<div class="alert"><b>Warning</b>  If this member is not set to NULL, the <b>CurrentReceiveFilterCapabilities</b> member must not be set to <b>NULL</b>.</div>
<div> </div>
        
            `HardwareSriovCapabilities`

            A pointer to an <a href="..\ntddndis\ns-ntddndis-_ndis_sriov_capabilities.md">NDIS_SRIOV_CAPABILITIES</a> structure. This structure specifies the single root I/O virtualization (SR-IOV) capabilities of the network adapter hardware. This value can be <b>NULL</b> if the network adapter does not support SR-IOV.

For more information on SR-IOV, see <a href="https://msdn.microsoft.com/E64DD4F0-D5F8-4FFF-931B-C04C5C42D000">Single Root I/O Virtualization (SR-IOV)</a>.

<div class="alert"><b>Note</b>  If this member is not set to NULL, the <b>CurrentSriovCapabilities</b>, <b>HardwareNicSwitchCapabilities</b>, and <b>CurrentNicSwitchCapabilities</b> members must not be set to <b>NULL</b>.</div>
<div> </div>
        
            `HDSplitAttributes`

            A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_hd_split_attributes.md">NDIS_HD_SPLIT_ATTRIBUTES</a> structure
     that represents the header-data split capabilities that the network adapter provides. If the network adapter does not support the header-data split feature, set 
     <b>HDSplitAttributes</b> to <b>NULL</b>.
        
            `Header`

            The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</b> structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES.
     

To indicate the version of the <b>NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</b> structure, set the 
     <b>Revision</b> member to one of the following values:

    ## Remarks
        To register the hardware-assisted capabilities of the underlying network adapter, the miniport driver calls the 
    <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
    NdisMSetMiniportAttributes</a> function from its 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function. The driver passes 
    an initialized <b>NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</b>
    structure to the <i>MiniportAttributes</i> parameter of this function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_hd_split_attributes.md">NDIS_HD_SPLIT_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_capabilities.md">NDIS_NIC_SWITCH_CAPABILITIES</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_receive_filter_capabilities.md">
   NDIS_RECEIVE_FILTER_CAPABILITIES</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_qos_capabilities.md">NDIS_QOS_CAPABILITIES</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_sriov_capabilities.md">NDIS_SRIOV_CAPABILITIES</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>