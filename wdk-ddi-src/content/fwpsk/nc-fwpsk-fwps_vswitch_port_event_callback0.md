---
UID: NC.fwpsk.FWPS_VSWITCH_PORT_EVENT_CALLBACK0
title: FWPS_VSWITCH_PORT_EVENT_CALLBACK0
author: windows-driver-content
description: The filter engine calls the vSwitchPortEventNotifyFn (FWPS_VSWITCH_PORT_EVENT_CALLBACK0) callout function to notify the callout driver about events that are associated a virtual switch (vSwitch) port.Note  FWPS_VSWITCH_PORT_EVENT_CALLBACK0 is a specific version of FWPS_VSWITCH_PORT_EVENT_CALLBACK. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwps_vswitch_port_event_callback0.htm
old-project: netvista
ms.assetid: CE4B14BE-5ECA-4C2F-809C-B0DC27EC2FF2
ms.author: windowsdriverdev
ms.date: 12/6/2017
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
req.alt-api: vSwitchPortEventNotifyFn
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
---

# FWPS_VSWITCH_PORT_EVENT_CALLBACK0 callback



## -description
The filter engine calls the 
  
  <i>vSwitchPortEventNotifyFn</i>   (<i>FWPS_VSWITCH_PORT_EVENT_CALLBACK0</i>) callout function to notify the callout driver about events that are
  associated a virtual switch (vSwitch) port.<div class="alert"><b>Note</b>  <i>FWPS_VSWITCH_PORT_EVENT_CALLBACK0</i> is a specific version of <i>FWPS_VSWITCH_PORT_EVENT_CALLBACK</i>. See <a href="fwp.wfp_version-independent_names_and_targeting_specific_versions_of_windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -prototype

````
FWPS_VSWITCH_PORT_EVENT_CALLBACK0 vSwitchPortEventNotifyFn;

NTSTATUS NTAPI vSwitchPortEventNotifyFn(
  _In_opt_       void                        *notifyContext,
  _In_            void                       *completionContext,
  _In_           FWPS_VSWITCH_EVENT_TYPE     eventType,
  _In_     const  NDIS_SWITCH_PARAMETERS     *vSwitch,
  _In_     const NDIS_SWITCH_PORT_PARAMETERS *vSwitchPort
)
{ ... }
````


## -parameters

### -param notifyContext [in, optional]

A pointer to a context provided by the callout driver. The driver passed this pointer to the <i>notifyContext</i> parameter of the <a href="netvista.fwpsvswitcheventssubscribe0">FwpsvSwitchEventsSubscribe0</a>
 function. This parameter is optional and can be NULL.

### -param completionContext [in]

A pointer to a completion context provided by the callout driver. This parameter is optional and can be NULL.



### -param eventType [in]

The type of virtual switch vSwitch event  specified as one of the <a href="netvista.fwps_vswitch_event_type">FWPS_VSWITCH_EVENT_TYPE</a> enumeration values. For more information, see Remarks.

### -param vSwitch [in]

A pointer to an <a href="netvista.ndis_switch_parameters">NDIS_SWITCH_PARAMETERS</a> structure that contains information about a virtual switch.
  

<div class="alert"><b>Note</b>  The information in the <a href="netvista.ndis_switch_parameters">NDIS_SWITCH_PARAMETERS</a> structure reflects the initial state of the virtual switch, not necessarily its current state. In particular, the <b>NumSwitchPorts</b> and <b>IsActive</b> members might still have their initial value of zero, unless a virtual switch PnP event has been triggered. Current state information can be found in the other parameters to this callback function.</div>
<div> </div>

### -param vSwitchPort [in]

A pointer to an <a href="netvista.ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETERS</a> structure that contains  parameters for a port on a vSwitch.  


## -returns
A callout's 
  
  <i>FWPS_VSWITCH_PORT_EVENT_CALLBACK0</i> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The callout driver accepts the notification from the filter engine.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl> The operation is pending and will be completed later.  The callout  driver will  call the <a href="netvista.fwpsvswitchnotifycomplete0">FwpsvSwitchNotifyComplete0</a> function to complete the pending operation.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred. 

 

## -remarks
A callout driver registers a 
  
  <i>vSwitchPortEventNotifyFn</i> function  by calling  
    
    the <a href="netvista.fwpsvswitcheventssubscribe0">FwpsvSwitchEventsSubscribe0</a>
 function.

If the <i>vSwitchPortEventNotifyFn</i> callback is registered, the callout driver receives notifications  for port creation and deletion.

If the <i>eventType</i> parameter  is set to FWPS_VSWITCH_EVENT_PORT_CREATE, a vSwitch port was created. 
In this case, the <i>vSwitch</i> parameter identifies an <a href="netvista.ndis_switch_parameters">NDIS_SWITCH_PARAMETERS</a> structure that contains information about the virtual switch (vSwitch) and the <a href="netvista.ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETERS</a> parameter contains information about the port. 


A callout can return STATUS_PENDING from <i>vSwitchPortEventNotifyFn</i>. In this case, the callout  driver calls the <a href="netvista.fwpsvswitchnotifycomplete0">FwpsvSwitchNotifyComplete0</a> function to complete the pending operation.

After the port is deleted, the WFP filter driver calls <i>vSwitchPortEventNotifyFn</i> with FWPS_VSWITCH_EVENT_PORT_DELETE set in the <i>eventType</i> parameter.


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
<a href="netvista.fwps_vswitch_event_type">FWPS_VSWITCH_EVENT_TYPE</a>
</dt>
<dt>
<a href="netvista.fwpsvswitcheventssubscribe0">FwpsvSwitchEventsSubscribe0</a>
</dt>
<dt>
<a href="netvista.fwpsvswitchnotifycomplete0">FwpsvSwitchNotifyComplete0</a>
</dt>
<dt>
<a href="netvista.ndis_switch_parameters">NDIS_SWITCH_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.callout_driver_callout_functions">Callout Driver Callout Functions</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_VSWITCH_PORT_EVENT_CALLBACK0 callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
