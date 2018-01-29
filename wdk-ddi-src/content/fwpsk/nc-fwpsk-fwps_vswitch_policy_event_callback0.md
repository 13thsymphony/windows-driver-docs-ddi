---
UID : NC:fwpsk.FWPS_VSWITCH_POLICY_EVENT_CALLBACK0
title : FWPS_VSWITCH_POLICY_EVENT_CALLBACK0
author : windows-driver-content
description : The filter engine calls the vSwitchPolicyEventNotifyFn (FWPS_VSWITCH_POLICY_EVENT_CALLBACK0) callout function to notify the callout driver about virtual switch policy events.Note  FWPS_VSWITCH_POLICY_EVENT_CALLBACK0 is a specific version of FWPS_VSWITCH_POLICY_EVENT_CALLBACK. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location : netvista\fwps_vswitch_policy_event_callback0.htm
old-project : netvista
ms.assetid : 8D0F61E2-A891-4D51-9E33-BFA491B95505
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.fwps_vswitch_policy_event_callback0, vSwitchPolicyEventNotifyFn callback function [Network Drivers Starting with Windows Vista], vSwitchPolicyEventNotifyFn, FWPS_VSWITCH_POLICY_EVENT_CALLBACK0, FWPS_VSWITCH_POLICY_EVENT_CALLBACK0, fwpsk/vSwitchPolicyEventNotifyFn
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : fwpsk.h
req.include-header : Fwpsk.h
req.target-type : Windows
req.target-min-winverclnt : Available starting with Windows 8.
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
req.irql : <= DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PINSTANCE_PARTIAL_INFORMATION, INSTANCE_PARTIAL_INFORMATION
---


# FWPS_VSWITCH_POLICY_EVENT_CALLBACK0 callback function
The filter engine calls the 
  
  <i>vSwitchPolicyEventNotifyFn</i> (<i>FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</i>) callout function to notify the callout driver about virtual switch policy events.<div class="alert"><b>Note</b>  <i>FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</i> is a specific version of <i>FWPS_VSWITCH_POLICY_EVENT_CALLBACK</i>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>

## Syntax

```
FWPS_VSWITCH_POLICY_EVENT_CALLBACK0 FwpsVswitchPolicyEventCallback0;

NTSTATUS FwpsVswitchPolicyEventCallback0(
  void *notifyContext,
  void *completionContext,
  FWPS_VSWITCH_EVENT_TYPE eventType,
  const NDIS_SWITCH_PARAMETERS *vSwitch,
  const NDIS_SWITCH_PORT_PROPERTY_PARAMETERS *vSwitchPortProperty,
  const NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS *vSwitchPortPropertyDelete
)
{...}
```

## Parameters

`*notifyContext`



`*completionContext`



`eventType`

The type of virtual switch event  specified as one of the <a href="..\fwpsk\ne-fwpsk-fwps_vswitch_event_type_.md">FWPS_VSWITCH_EVENT_TYPE</a> enumeration values. For more information, see Remarks.

`*vSwitch`



`*vSwitchPortProperty`



`*vSwitchPortPropertyDelete`




## Return Value

A callout's 
  
  <i>FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</i> function returns one of the following NTSTATUS codes.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The callout driver accepts the notification from the filter engine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
 The operation is pending and will be completed later.  The callout  driver will  call the <a href="..\fwpsk\nf-fwpsk-fwpsvswitchnotifycomplete0.md">FwpsvSwitchNotifyComplete0</a> function to complete the pending operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. 

</td>
</tr>
</table>

## Remarks

A callout driver registers a 
  
  <i>vSwitchPolicyEventNotifyFn</i> function  by calling  
    
    the <a href="..\fwpsk\nf-fwpsk-fwpsvswitcheventssubscribe0.md">FwpsvSwitchEventsSubscribe0</a>
 function.

If the <i>vSwitchPolicyEventNotifyFn</i> callback is registered, the callout on the target host will be notified about the policy configured for the virtual switch port during live migration and before the migrating VM can run on the new host. 

Without live migration, <i>vSwitchPolicyEventNotifyFn</i> will also be invoked for a VM save operation. 

Changes to vendor filtering policies that are configured through the VMMS WMI interface are passed to the WFP virtual switch extension with OID requests.  These OIDs carry a <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_parameters.md">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a> structure with the <b>PropertyType</b> member set to the  <b>NdisSwitchPortPropertyTypeCustom</b> type.

The WFP filter driver passes the information in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598275">OID_SWITCH_PORT_PROPERTY_ADD</a> OID request  to <i>vSwitchPolicyEventNotifyFn</i> with the    FWPS_VSWITCH_EVENT_POLICY_ADD type set in the <i>eventType</i> parameter  to notify  callout drivers about the addition of a policy property for a virtual switch port.


The WFP filter driver passes the information in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598278">OID_SWITCH_PORT_PROPERTY_UPDATE</a> OID request  to <i>vSwitchPolicyEventNotifyFn</i> with the    FWPS_VSWITCH_EVENT_POLICY_UPDATE type set in the <i>eventType</i> parameter   to notify callout filter drivers about the update of a property for a virtual switch port policy.


These OIDs also include a property identifier GUID that uniquely identifies which WFP provider the policy belongs to. The property identifier GUID is provided when an vendor  configures its policy through VMMS, and the GUID must be the same GUID the vendor uses to register its provider with WFP.

WFP attempts to match the property identifier GUID with the provider GUID specified from the <a href="..\fwpsk\nf-fwpsk-fwpsvswitcheventssubscribe0.md">FwpsvSwitchEventsSubscribe0</a> function. If there is a match, WFP invokes the corresponding <i>vSwitchPolicyEventNotifyFn</i> and passes the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_parameters.md">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a> structure to the callout.

The WFP filter driver passes the information in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598276">OID_SWITCH_PORT_PROPERTY_DELETE</a> OID request  to <i>vSwitchPolicyEventNotifyFn</i> with the    FWPS_VSWITCH_EVENT_POLICY_DELETE type set in the <i>eventType</i> parameter  to notify callout filter drivers about the deletion of a policy property for a virtual switch port. The delete properties are specified in the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_delete_parameters.md">NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</a> structure.


If the callout returns STATUS_PENDING from <i>vSwitchPolicyEventNotifyFn</i>, WFP returns STATUS_PENDING to the <a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a> handler.   The callout  driver will  call the <a href="..\fwpsk\nf-fwpsk-fwpsvswitchnotifycomplete0.md">FwpsvSwitchNotifyComplete0</a> function to complete the pending operation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fwpsk.h (include Fwpsk.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\fwpsk\ne-fwpsk-fwps_vswitch_event_type_.md">FWPS_VSWITCH_EVENT_TYPE</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_switch_parameters.md">NDIS_SWITCH_PARAMETERS</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_delete_parameters.md">NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598275">OID_SWITCH_PORT_PROPERTY_ADD</a>

<a href="..\fwpsk\nf-fwpsk-fwpsvswitchnotifycomplete0.md">FwpsvSwitchNotifyComplete0</a>

<a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598276">OID_SWITCH_PORT_PROPERTY_DELETE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543875">Callout Driver Callout Functions</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_parameters.md">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598278">OID_SWITCH_PORT_PROPERTY_UPDATE</a>

<a href="..\fwpsk\nf-fwpsk-fwpsvswitcheventssubscribe0.md">FwpsvSwitchEventsSubscribe0</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_VSWITCH_POLICY_EVENT_CALLBACK0 callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>