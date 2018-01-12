---
UID: NC:fwpsk.FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0
title: FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0
author: windows-driver-content
description: The filter engine calls the vSwitchInterfaceEventNotifyFn (FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0) callout function to notify the callout driver about events that are associated the virtual switch interface.Note  FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0 is a specific version of FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwps_vswitch_interface_event_callback0.htm
old-project: netvista
ms.assetid: 63EAA278-9CE6-4C75-8221-E1666F143815
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: FwpmEngineOpen0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: vSwitchInterfaceEventNotifyFn
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
req.typenames: PINSTANCE_PARTIAL_INFORMATION, INSTANCE_PARTIAL_INFORMATION
---

# FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0 callback



## -description
The filter engine calls the <i>vSwitchInterfaceEventNotifyFn</i>  
  
  (<i>FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0</i>) callout function to notify the callout driver about events that are
  associated the virtual switch  interface.<div class="alert"><b>Note</b>  <i>FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0</i> is a specific version of <i>FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK</i>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>




## -prototype

````
FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0 vSwitchInterfaceEventNotifyFn;

NTSTATUS NTAPI vSwitchInterfaceEventNotifyFn(
  _In_opt_       void                       *notifyContext,
  _In_           void                       *completionContext,
  _In_           FWPS_VSWITCH_EVENT_TYPE    eventType,
  _In_     const NDIS_SWITCH_PARAMETERS     *vSwitch,
  _In_     const NDIS_SWITCH_NIC_PARAMETERS *vSwitchNic
)
{ ... }
````


## -parameters

### -param notifyContext [in, optional]

A pointer to a context provided by the callout driver. The driver passed this pointer to the <i>notifyContext</i> parameter of the <a href="..\fwpsk\nf-fwpsk-fwpsvswitcheventssubscribe0.md">FwpsvSwitchEventsSubscribe0</a>
 function. This parameter is optional and can be NULL.


### -param completionContext [in]

A pointer to a completion context provided by the callout driver. This parameter is optional and can be NULL.




### -param eventType [in]

The type of virtual switch event  specified as one of the <a href="..\fwpsk\ne-fwpsk-fwps_vswitch_event_type_.md">FWPS_VSWITCH_EVENT_TYPE</a> enumeration values. For more information, see Remarks.


### -param vSwitch [in]

A pointer to an <a href="..\ntddndis\ns-ntddndis-_ndis_switch_parameters.md">NDIS_SWITCH_PARAMETERS</a> structure that contains information about a virtual switch.


<div class="alert"><b>Note</b>  The information in the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_parameters.md">NDIS_SWITCH_PARAMETERS</a> structure reflects the initial state of the virtual switch, not necessarily its current state. In particular, the <b>NumSwitchPorts</b> and <b>IsActive</b> members might still have their initial value of zero, unless a virtual switch PnP event has been triggered. Current state information can be found in the other parameters to this callback function.</div>
<div> </div>

### -param vSwitchNic [in]

A pointer to an <a href="..\ntddndis\ns-ntddndis-_ndis_switch_nic_parameters.md">NDIS_SWITCH_NIC_PARAMETERS</a> structure that specifies the parameters for a virtual miniport adapter that is connected to a virtual switch  port. 



## -returns
A callout's 
  
  <i>FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0</i> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The callout driver accepts the notification from the filter engine.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred. 

 


## -remarks
A callout driver registers a 
  
  <i>vSwitchInterfaceEventNotifyFn</i> function  by calling  
    
    the <a href="..\fwpsk\nf-fwpsk-fwpsvswitcheventssubscribe0.md">FwpsvSwitchEventsSubscribe0</a>
 function.

If the <i>eventType</i> parameter  is set to WPS_VSWITCH_EVENT_INTERFACE_CREATE, a new network connection between a virtual switch port and a network adapter is completely established. The <i>vSwitchNic</i> parameter identifies an <a href="..\ntddndis\ns-ntddndis-_ndis_switch_nic_parameters.md">NDIS_SWITCH_NIC_PARAMETERS</a> structure that contains information about the virtual network adapter that is connected to the virtual switch port. 



   If the <i>eventType</i> parameter is FWPS_VSWITCH_EVENT_INTERFACE_DISCONNECT, the connection between a virtual switch port and a network adapter is being torn down. After the connection has been completely torn down, the WFP filter driver will  call <i>vSwitchInterfaceEventNotifyFn</i> with FWPS_VSWITCH_EVENT_INTERFACE_DELETE set in the <i>eventType</i> parameter.



## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fwpsk\ne-fwpsk-fwps_vswitch_event_type_.md">FWPS_VSWITCH_EVENT_TYPE</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsvswitcheventssubscribe0.md">FwpsvSwitchEventsSubscribe0</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_switch_nic_parameters.md">NDIS_SWITCH_NIC_PARAMETERS</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_switch_parameters.md">NDIS_SWITCH_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543875">Callout Driver Callout Functions</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_VSWITCH_INTERFACE_EVENT_CALLBACK0 callback function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

