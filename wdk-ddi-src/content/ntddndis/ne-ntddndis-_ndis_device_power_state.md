---
UID: NE:ntddndis._NDIS_DEVICE_POWER_STATE
title: "_NDIS_DEVICE_POWER_STATE"
author: windows-driver-content
description: The NDIS_DEVICE_POWER_STATE enumeration defines device power state values.
old-location: netvista\ndis_device_power_state.htm
old-project: netvista
ms.assetid: d241b0ee-7b13-453d-ac6a-015b82effb95
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NDIS_DEVICE_POWER_STATE, NdisDeviceStateMaximum, *PNDIS_DEVICE_POWER_STATE, ntddndis/NdisDeviceStateD0, ntddndis/NDIS_DEVICE_POWER_STATE, NdisDeviceStateD3, NdisDeviceStateD2, ntddndis/NdisDeviceStateMaximum, PNDIS_DEVICE_POWER_STATE, NdisDeviceStateD1, ntddndis/PNDIS_DEVICE_POWER_STATE, ntddndis/NdisDeviceStateD3, netvista.ndis_device_power_state, ntddndis/NdisDeviceStateD2, _NDIS_DEVICE_POWER_STATE, PNDIS_DEVICE_POWER_STATE enumeration pointer [Network Drivers Starting with Windows Vista], NdisDeviceStateD0, ntddndis/NdisDeviceStateD1, ntddndis/NdisDeviceStateUnspecified, NdisDeviceStateUnspecified, NDIS_DEVICE_POWER_STATE enumeration [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddndis.h
apiname:
-	NDIS_DEVICE_POWER_STATE
product: Windows
targetos: Windows
req.typenames: NDIS_DEVICE_POWER_STATE, *PNDIS_DEVICE_POWER_STATE
---

# _NDIS_DEVICE_POWER_STATE Enumeration
The <b>NDIS_DEVICE_POWER_STATE</b> enumeration defines device power state values. For more information about device power states, see:<dl>
<dd>
<a href="https://msdn.microsoft.com/969aadc9-e797-4a07-9714-8c2c5a6357da">Device Power States for Network Adapters</a>
</dd>
<dd>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543162">Device Power States</a>
</dd>
<dd>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543210">Device Working State D0</a>
</dd>
<dd>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543186">Device Low-Power States</a>
</dd>
<dd>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561073">Required Support for Device Power States</a>
</dd>
</dl>

## Syntax
````
typedef enum _NDIS_DEVICE_POWER_STATE { 
  NdisDeviceStateUnspecified  = 0,
  NdisDeviceStateD0           = 1,
  NdisDeviceStateD1           = 2,
  NdisDeviceStateD2           = 3,
  NdisDeviceStateD3           = 4,
  NdisDeviceStateMaximum      = 5
} NDIS_DEVICE_POWER_STATE, *PNDIS_DEVICE_POWER_STATE;
````

## Constants

<table>
            
                <tr>
                    <td>NdisDeviceStateD0</td>
                    <td>Device power state D0.</td>
                </tr>
            
                <tr>
                    <td>NdisDeviceStateD1</td>
                    <td>Device power state D1.</td>
                </tr>
            
                <tr>
                    <td>NdisDeviceStateD2</td>
                    <td>Device power state D2.</td>
                </tr>
            
                <tr>
                    <td>NdisDeviceStateD3</td>
                    <td>Device power state D3.</td>
                </tr>
            
                <tr>
                    <td>NdisDeviceStateMaximum</td>
                    <td>The maximum value for this enumeration. Reserved for system use. Do not use this value in your driver. This value might change in future versions of NDIS header files and binaries.</td>
                </tr>
            
                <tr>
                    <td>NdisDeviceStateUnspecified</td>
                    <td>The device does not support power management.</td>
                </tr>
</table>

    ## Remarks

        Depending on the capabilities of the network adapter and its miniport driver, the device might be able to generate a wake-up signal from device states D0 through D3.

<div class="alert"><b>Note</b>  If the wake-up signal is generated from D0, the signal does not cause a system wake-up. However, the wake-up signal can be used to signal a run-time event.</div>
<div> </div>
<b>NDIS_DEVICE_POWER_STATE</b> enumeration values are used in the <a href="..\ntddndis\ns-ntddndis-_ndis_pm_capabilities.md">NDIS_PM_CAPABILITIES</a>, <a href="..\ntddndis\ns-ntddndis-_ndis_sriov_set_vf_power_state_parameters.md">NDIS_SRIOV_SET_VF_POWER_STATE_PARAMETERS</a>,  and <a href="..\ndis\ns-ndis-_net_pnp_event.md">NET_PNP_EVENT</a> structures, the <a href="..\ndis\nf-ndis-ndismidlenotificationconfirm.md">NdisMIdleNotificationConfirm</a> function, and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569774">OID_PNP_CAPABILITIES</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff569778">OID_PNP_QUERY_POWER</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff569780">OID_PNP_SET_POWER</a> OID requests.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddndis.h |

    ## See Also

        <a href="..\ndis\ns-ndis-_net_pnp_event.md">NET_PNP_EVENT</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_pm_capabilities.md">NDIS_PM_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569780">OID_PNP_SET_POWER</a>



<a href="..\ndis\nf-ndis-ndismidlenotificationconfirm.md">NdisMIdleNotificationConfirm</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569778">OID_PNP_QUERY_POWER</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_sriov_set_vf_power_state_parameters.md">NDIS_SRIOV_SET_VF_POWER_STATE_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569774">OID_PNP_CAPABILITIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_DEVICE_POWER_STATE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>