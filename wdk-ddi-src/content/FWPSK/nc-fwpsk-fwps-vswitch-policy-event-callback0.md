---
UID: NC.fwpsk.FWPS_VSWITCH_POLICY_EVENT_CALLBACK0
title: FWPS_VSWITCH_POLICY_EVENT_CALLBACK0
author: windows-driver-content
description: The filter engine calls the vSwitchPolicyEventNotifyFn (FWPS_VSWITCH_POLICY_EVENT_CALLBACK0) callout function to notify the callout driver about virtual switch policy events.Note  FWPS_VSWITCH_POLICY_EVENT_CALLBACK0 is a specific version of FWPS_VSWITCH_POLICY_EVENT_CALLBACK. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwps_vswitch_policy_event_callback0.htm
ms.assetid: 8D0F61E2-A891-4D51-9E33-BFA491B95505
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: netvista
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: vSwitchPolicyEventNotifyFn
req.alt-loc: fwpsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
ms.keywords: FwpmEngineOpen0
req.iface: 
---

# FWPS_VSWITCH_POLICY_EVENT_CALLBACK0 callback



## -description
<p>The filter engine calls the 
  
  <i>vSwitchPolicyEventNotifyFn</i> (<i>FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</i>) callout function to notify the callout driver about virtual switch policy events.<div class="alert"><b>Note</b>  <i>FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</i> is a specific version of <i>FWPS_VSWITCH_POLICY_EVENT_CALLBACK</i>. See <a href="fwp.wfp_version-independent_names_and_targeting_specific_versions_of_windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>
</p>


## -prototype

````
FWPS_VSWITCH_POLICY_EVENT_CALLBACK0 vSwitchPolicyEventNotifyFn;

NTSTATUS NTAPI vSwitchPolicyEventNotifyFn(
  _In_opt_       void                                                                                                               *notifyContext,
  _In_           void                                                                                                               *completionContext,
  _In_           FWPS_VSWITCH_EVENT_TYPE                                                                                            eventType,
  _In_     const NDIS_SWITCH_PARAMETERS                                                                                             *vSwitch,
  _In_opt_       _When_(eventType == FWPS_VSWITCH_EVENT_POLICY_DELETE, _Null_) const NDIS_SWITCH_PORT_PROPERTY_PARAMETERS           *vSwitchPortProperty,
  _In_opt_       _When_(eventType == FWPS_VSWITCH_EVENT_POLICY_DELETE, _Notnull_) const NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS *vSwitchPortPropertyDelete
)
{ ... }
````


## -parameters
<dl>

### -param <i>notifyContext</i> [in, optional]

<dd>
<p>A pointer to a context provided by the callout driver. The driver passed this pointer to the <i>notifyContext</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a>
 function. This parameter is optional and can be NULL.</p>
</dd>

### -param <i>completionContext</i> [in]

<dd>
<p>A pointer to a completion context provided by the callout driver. This parameter is optional and can be NULL.

</p>
</dd>

### -param <i>eventType</i> [in]

<dd>
<p>The type of virtual switch event  specified as one of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451265">FWPS_VSWITCH_EVENT_TYPE</a> enumeration values. For more information, see Remarks.</p>
</dd>

### -param <i>vSwitch</i> [in]

<dd>
<p>A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598220">NDIS_SWITCH_PARAMETERS</a> structure that contains information about a virtual switch.</p>
<div class="alert"><b>Note</b>  The information in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598220">NDIS_SWITCH_PARAMETERS</a> structure reflects the initial state of the virtual switch, not necessarily its current state. In particular, the <b>NumSwitchPorts</b> and <b>IsActive</b> members might still have their initial value of zero, unless a virtual switch PnP event has been triggered. Current state information can be found in the other parameters to this callback function.</div>
<div> </div>
</dd>

### -param <i>vSwitchPortProperty</i> [in, optional]

<dd>
<p>A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598238">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a> structure. The virtual switch port property.</p>
</dd>

### -param <i>vSwitchPortPropertyDelete</i> [in, optional]

<dd>
<p>A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598232">NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</a> structure. The virtual switch port property.</p>
</dd>
</dl>

## -returns
<p>A callout's 
  
  <i>FWPS_VSWITCH_POLICY_EVENT_CALLBACK0</i> function returns one of the following NTSTATUS codes.</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The callout driver accepts the notification from the filter engine.</p><dl>
<dt><b>STATUS_PENDING</b></dt>
</dl><p> The operation is pending and will be completed later.  The callout  driver will  call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439695">FwpsvSwitchNotifyComplete0</a> function to complete the pending operation.</p><dl>
<dt><b>Other status codes</b></dt>
</dl><p>An error occurred. </p>

<p> </p>

## -remarks
<p>A callout driver registers a 
  
  <i>vSwitchPolicyEventNotifyFn</i> function  by calling  
    
    the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a>
 function.</p>

<p>If the <i>vSwitchPolicyEventNotifyFn</i> callback is registered, the callout on the target host will be notified about the policy configured for the virtual switch port during live migration and before the migrating VM can run on the new host. </p>

<p>Without live migration, <i>vSwitchPolicyEventNotifyFn</i> will also be invoked for a VM save operation. </p>

<p>Changes to vendor filtering policies that are configured through the VMMS WMI interface are passed to the WFP virtual switch extension with OID requests.  These OIDs carry a <a href="https://msdn.microsoft.com/library/windows/hardware/hh598238">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a> structure with the <b>PropertyType</b> member set to the  <b>NdisSwitchPortPropertyTypeCustom</b> type.</p>

<p>The WFP filter driver passes the information in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598275">OID_SWITCH_PORT_PROPERTY_ADD</a> OID request  to <i>vSwitchPolicyEventNotifyFn</i> with the    FWPS_VSWITCH_EVENT_POLICY_ADD type set in the <i>eventType</i> parameter  to notify  callout drivers about the addition of a policy property for a virtual switch port.
</p>

<p>The WFP filter driver passes the information in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598278">OID_SWITCH_PORT_PROPERTY_UPDATE</a> OID request  to <i>vSwitchPolicyEventNotifyFn</i> with the    FWPS_VSWITCH_EVENT_POLICY_UPDATE type set in the <i>eventType</i> parameter   to notify callout filter drivers about the update of a property for a virtual switch port policy.
</p>

<p>These OIDs also include a property identifier GUID that uniquely identifies which WFP provider the policy belongs to. The property identifier GUID is provided when an vendor  configures its policy through VMMS, and the GUID must be the same GUID the vendor uses to register its provider with WFP.</p>

<p>WFP attempts to match the property identifier GUID with the provider GUID specified from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a> function. If there is a match, WFP invokes the corresponding <i>vSwitchPolicyEventNotifyFn</i> and passes the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598238">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a> structure to the callout.</p>

<p>The WFP filter driver passes the information in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598276">OID_SWITCH_PORT_PROPERTY_DELETE</a> OID request  to <i>vSwitchPolicyEventNotifyFn</i> with the    FWPS_VSWITCH_EVENT_POLICY_DELETE type set in the <i>eventType</i> parameter  to notify callout filter drivers about the deletion of a policy property for a virtual switch port. The delete properties are specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598232">NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</a> structure.
</p>

<p>If the callout returns STATUS_PENDING from <i>vSwitchPolicyEventNotifyFn</i>, WFP returns STATUS_PENDING to the <a href="https://msdn.microsoft.com/238bfa21-a971-4fe4-a774-6ba834efc3c5">FilterOidRequest</a> handler.   The callout  driver will  call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439695">FwpsvSwitchNotifyComplete0</a> function to complete the pending operation.</p>

<p>A callout driver registers a 
  
  <i>vSwitchPolicyEventNotifyFn</i> function  by calling  
    
    the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a>
 function.</p>

<p>If the <i>vSwitchPolicyEventNotifyFn</i> callback is registered, the callout on the target host will be notified about the policy configured for the virtual switch port during live migration and before the migrating VM can run on the new host. </p>

<p>Without live migration, <i>vSwitchPolicyEventNotifyFn</i> will also be invoked for a VM save operation. </p>

<p>Changes to vendor filtering policies that are configured through the VMMS WMI interface are passed to the WFP virtual switch extension with OID requests.  These OIDs carry a <a href="https://msdn.microsoft.com/library/windows/hardware/hh598238">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a> structure with the <b>PropertyType</b> member set to the  <b>NdisSwitchPortPropertyTypeCustom</b> type.</p>

<p>The WFP filter driver passes the information in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598275">OID_SWITCH_PORT_PROPERTY_ADD</a> OID request  to <i>vSwitchPolicyEventNotifyFn</i> with the    FWPS_VSWITCH_EVENT_POLICY_ADD type set in the <i>eventType</i> parameter  to notify  callout drivers about the addition of a policy property for a virtual switch port.
</p>

<p>The WFP filter driver passes the information in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598278">OID_SWITCH_PORT_PROPERTY_UPDATE</a> OID request  to <i>vSwitchPolicyEventNotifyFn</i> with the    FWPS_VSWITCH_EVENT_POLICY_UPDATE type set in the <i>eventType</i> parameter   to notify callout filter drivers about the update of a property for a virtual switch port policy.
</p>

<p>These OIDs also include a property identifier GUID that uniquely identifies which WFP provider the policy belongs to. The property identifier GUID is provided when an vendor  configures its policy through VMMS, and the GUID must be the same GUID the vendor uses to register its provider with WFP.</p>

<p>WFP attempts to match the property identifier GUID with the provider GUID specified from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a> function. If there is a match, WFP invokes the corresponding <i>vSwitchPolicyEventNotifyFn</i> and passes the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598238">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a> structure to the callout.</p>

<p>The WFP filter driver passes the information in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598276">OID_SWITCH_PORT_PROPERTY_DELETE</a> OID request  to <i>vSwitchPolicyEventNotifyFn</i> with the    FWPS_VSWITCH_EVENT_POLICY_DELETE type set in the <i>eventType</i> parameter  to notify callout filter drivers about the deletion of a policy property for a virtual switch port. The delete properties are specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598232">NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</a> structure.
</p>

<p>If the callout returns STATUS_PENDING from <i>vSwitchPolicyEventNotifyFn</i>, WFP returns STATUS_PENDING to the <a href="https://msdn.microsoft.com/238bfa21-a971-4fe4-a774-6ba834efc3c5">FilterOidRequest</a> handler.   The callout  driver will  call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439695">FwpsvSwitchNotifyComplete0</a> function to complete the pending operation.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/238bfa21-a971-4fe4-a774-6ba834efc3c5">FilterOidRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451265">FWPS_VSWITCH_EVENT_TYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439687">FwpsvSwitchEventsSubscribe0</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439695">FwpsvSwitchNotifyComplete0</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598220">NDIS_SWITCH_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598232">NDIS_SWITCH_PORT_PROPERTY_DELETE_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598238">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598275">OID_SWITCH_PORT_PROPERTY_ADD</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598276">OID_SWITCH_PORT_PROPERTY_DELETE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598278">OID_SWITCH_PORT_PROPERTY_UPDATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543875">Callout Driver Callout Functions</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_VSWITCH_POLICY_EVENT_CALLBACK0 callback function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
