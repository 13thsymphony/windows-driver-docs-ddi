---
UID: NC.ndis.PROTOCOL_NET_PNP_EVENT
title: PROTOCOL_NET_PNP_EVENT
author: windows-driver-content
description: NDIS calls the ProtocolNetPnPEvent function to indicate a network Plug and Play event, an NDIS PnP event, or a power management event to a protocol driver.Note  You must declare the function by using the PROTOCOL_NET_PNP_EVENT type.
old-location: netvista\protocolnetpnpevent.htm
ms.assetid: 3f50bcba-c7d2-4d81-bd8b-6080e08fbe74
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolNetPnPEvent
req.alt-loc: Ndis.h
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
ms.keywords: RxNameCacheInitialize
req.iface: 
---

# PROTOCOL_NET_PNP_EVENT callback



## -description
<p>NDIS calls the 
  <i>ProtocolNetPnPEvent</i> function to indicate a network Plug and Play event, an NDIS
  PnP event, or a power management event to a protocol driver.</p>


## -prototype

````
PROTOCOL_NET_PNP_EVENT ProtocolNetPnPEvent;

NDIS_STATUS ProtocolNetPnPEvent(
  _In_ NDIS_HANDLE                 ProtocolBindingContext,
  _In_ PNET_PNP_EVENT_NOTIFICATION NetPnPEvent
)
{ ... }
````


## -parameters
<dl>

### -param <i>ProtocolBindingContext</i> [in]

<dd>
<p>The handle to a protocol-driver-allocated context area in which this driver maintains per-binding
     run-time state information. The protocol driver supplied this handle when it called the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function. A 
     <b>NetEvent</b><i>Xxx</i> event that is indicated with a <b>NULL</b><i>ProtocolBindingContext</i> applies to all bindings. 
     <b>NetEventBindList</b> and 
     <b>NetEventBindsComplete</b> are always indicated with a <b>NULL</b><i>ProtocolBindingContext</i>. 
     <b>NetEventReconfigure</b> can be indicated with a specified 
     <i>ProtocolBindingContext</i> or with a <b>NULL</b><i>ProtocolBindingContext</i>.</p>
</dd>

### -param <i>NetPnPEvent</i> [in]

<dd>
<p>A pointer to a 
     <a href="https://msdn.microsoft.com/58d3baf3-a1fa-42ae-b795-2774a148aeda">
     NET_PNP_EVENT_NOTIFICATION</a> structure which describes the Plug and Play event or Power Management
     event that NDIS is indicating to the protocol driver.</p>
</dd>
</dl>

## -returns
<p><i>ProtocolNetPnPEvent</i> can return any of the following:</p><dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><p>The protocol driver successfully handled the indicated network Plug and Play event, NDIS PnP
       event, or power management event. The meaning of this status code depends on the 
       <b>NetEvent</b> code in the buffered 
       <a href="https://msdn.microsoft.com/58d3baf3-a1fa-42ae-b795-2774a148aeda">
       NET_PNP_EVENT_NOTIFICATION</a> structure at 
       <i>NetPnPEvent</i>:
       </p>

<p></p><dl>
<dt><a id="NetEventSetPower"></a><a id="neteventsetpower"></a><a id="NETEVENTSETPOWER"></a><b>NetEventSetPower</b></dt>
<dd>
<p>The protocol driver has performed any driver-specific actions that are required to prepare for
         the device's transition to the requested device power state.</p>
</dd>
<dt><a id="NetEventQueryPower"></a><a id="neteventquerypower"></a><a id="NETEVENTQUERYPOWER"></a><b>NetEventQueryPower</b></dt>
<dd>
<p>The underlying adapter can transition to the requested device power state.</p>
</dd>
<dt><a id="NetEventQueryRemoveDevice"></a><a id="neteventqueryremovedevice"></a><a id="NETEVENTQUERYREMOVEDEVICE"></a><b>NetEventQueryRemoveDevice</b></dt>
<dd>
<p>The underlying adapter can be removed.</p>
</dd>
<dt><a id="NetEventCancelRemoveDevice"></a><a id="neteventcancelremovedevice"></a><a id="NETEVENTCANCELREMOVEDEVICE"></a><b>NetEventCancelRemoveDevice</b></dt>
<dd>
<p>The protocol driver has performed any driver-specific actions that are required to prepare for
         the canceled removal of the underlying adapter.</p>
</dd>
<dt><a id="NetEventReconfigure"></a><a id="neteventreconfigure"></a><a id="NETEVENTRECONFIGURE"></a><b>NetEventReconfigure</b></dt>
<dd>
<p>The protocol driver has accepted the changed configuration.</p>
</dd>
<dt><a id="NetEventBindList"></a><a id="neteventbindlist"></a><a id="NETEVENTBINDLIST"></a><b>NetEventBindList</b></dt>
<dd>
<p>The protocol driver has the new bind list and has performed related processing.</p>
</dd>
<dt><a id="NetEventBindsComplete"></a><a id="neteventbindscomplete"></a><a id="NETEVENTBINDSCOMPLETE"></a><b>NetEventBindsComplete</b></dt>
<dd>
<p>The protocol driver has acknowledged the indication from NDIS that the protocol driver is
         bound to all available underlying adapters.</p>
</dd>
<dt><a id="NetEventPnPCapabilities"></a><a id="neteventpnpcapabilities"></a><a id="NETEVENTPNPCAPABILITIES"></a><b>NetEventPnPCapabilities</b></dt>
<dd>
<p>The protocol driver has acknowledged that it has received the current wake-up capabilities of
         the underlying adapter that is associated with the specified binding.</p>
</dd>
<dt><a id="NetEventPause"></a><a id="neteventpause"></a><a id="NETEVENTPAUSE"></a><b>NetEventPause</b></dt>
<dd>
<p>The specified protocol binding has entered the 
         <i>Pausing</i> state. The binding will enter the 
         <i>Paused</i> state after NDIS has completed all of the outstanding send requests
         for the binding. For more information about pause operations, see 
         <a href="NULL">Pausing a Binding</a>.</p>
</dd>
<dt><a id="NetEventRestart"></a><a id="neteventrestart"></a><a id="NETEVENTRESTART"></a><b>NetEventRestart</b></dt>
<dd>
<p>The specified protocol binding has entered the 
         <i>Restarting</i> state. After the protocol driver is ready to resume send and
         receive operations for the binding, the binding enters the 
         <i>Running</i> state.</p>
</dd>
<dt><a id="NetEventPortActivation"></a><a id="neteventportactivation"></a><a id="NETEVENTPORTACTIVATION"></a><b>NetEventPortActivation</b></dt>
<dd>
<p>The protocol driver has acknowledged the activation of a port that is associated with the
         specified binding. For more information about port activation, see 
         <a href="NULL">Activating an NDIS Port</a>.</p>
</dd>
<dt><a id="NetEventPortDeactivation"></a><a id="neteventportdeactivation"></a><a id="NETEVENTPORTDEACTIVATION"></a><b>NetEventPortDeactivation</b></dt>
<dd>
<p>The protocol driver has acknowledged the activation of a port that is associated with the
         specified binding.</p>
</dd>
</dl><p>The protocol driver has performed any driver-specific actions that are required to prepare for
         the device's transition to the requested device power state.</p>

<p>The underlying adapter can transition to the requested device power state.</p>

<p>The underlying adapter can be removed.</p>

<p>The protocol driver has performed any driver-specific actions that are required to prepare for
         the canceled removal of the underlying adapter.</p>

<p>The protocol driver has accepted the changed configuration.</p>

<p>The protocol driver has the new bind list and has performed related processing.</p>

<p>The protocol driver has acknowledged the indication from NDIS that the protocol driver is
         bound to all available underlying adapters.</p>

<p>The protocol driver has acknowledged that it has received the current wake-up capabilities of
         the underlying adapter that is associated with the specified binding.</p>

<p>The specified protocol binding has entered the 
         <i>Pausing</i> state. The binding will enter the 
         <i>Paused</i> state after NDIS has completed all of the outstanding send requests
         for the binding. For more information about pause operations, see 
         <a href="NULL">Pausing a Binding</a>.</p>

<p>The specified protocol binding has entered the 
         <i>Restarting</i> state. After the protocol driver is ready to resume send and
         receive operations for the binding, the binding enters the 
         <i>Running</i> state.</p>

<p>The protocol driver has acknowledged the activation of a port that is associated with the
         specified binding. For more information about port activation, see 
         <a href="NULL">Activating an NDIS Port</a>.</p>

<p>The protocol driver has acknowledged the activation of a port that is associated with the
         specified binding.</p><dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl><p>The protocol driver will return its response to the indicated event asynchronously with a call
       to the 
       <a href="https://msdn.microsoft.com/2a59e6a1-d018-4b95-8e50-8351a3b69d86">
       NdisCompleteNetPnPEvent</a> function.</p><dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl><p>The protocol driver could not obtain the necessary system resources to satisfy the indicated
       Plug and Play or Power Management event.</p><dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl><p>NDIS 6.0 and later protocol drivers must not return this status. An NDIS 5.<i>x</i> protocol driver that does
       not support Plug and Play can return this status in response to a 
       <b>NetEventSetPower</b> to indicate that NDIS should unbind it from the
       underlying adapter.</p><dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl><p>The protocol driver failed the indicated event for reasons other than those stated in the
       preceding list.</p>

<p> </p>

<p>A protocol driver can fail the 
      <b>NetEventQueryRemoveDevice</b> 
      and 
      <b>NetEventPortActivation</b> events.</p>

<p>If a protocol driver fails the 
      <b>NetEventPortActivation</b> event, it should not use any associated ports in
      subsequent operations.</p>

<p>A protocol driver should always succeed the 
      <b>NetEventRestart</b>, <b>NetEventIMReEnableDevice</b>, 
      <b>NetEventCancelRemoveDevice</b>, 
      <b>NetEventReconfigure</b>, 
      <b>NetEventBindList</b>, 
      <b>NetEventBindsComplete</b>, 
      <b>NetEventPause</b>, <b>NetEventPortDeactivation</b>, and 
      <b>NetEventPnPCapabilities</b> events by returning NDIS_STATUS_SUCCESS.</p>

## -remarks
<p>The 
    <i>ProtocolNetPnPEvent</i> function is required in protocol drivers to support Plug
    and Play and Power Management. NDIS calls 
    <i>ProtocolNetPnPEvent</i> to notify a protocol driver that a network Plug and Play
    event, an NDIS PnP event, or Power Management event has occurred.</p>

<p>The 
    <a href="https://msdn.microsoft.com/58d3baf3-a1fa-42ae-b795-2774a148aeda">
    NET_PNP_EVENT_NOTIFICATION</a> structure that is passed to 
    <i>ProtocolNetPnPEvent</i> describes the event. 
    <i>ProtocolNetPnPEvent</i> interprets two basic pieces of information in the
    NET_PNP_EVENT_NOTIFICATION structure:</p>

<p>A code in the 
      <b>NetEvent</b> member that identifies the type of Plug and Play or Power
      Management event.</p>

<p>Event-specific information. For example, with a 
      <b>NetEventSetPower</b> event the 
      <b>Buffer</b> member contains the device power state to which the device is
      transitioning.</p>

<p>The protocol driver should save the 
    <i>NetPnPEvent</i> pointer. This pointer is a required input parameter to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561705">NdisCompleteNetPnPEvent</a> function,
    which the protocol driver must subsequently call if 
    <i>ProtocolNetPnPEvent</i> returns NDIS_STATUS_PENDING.</p>

<p>A protocol driver should always succeed a 
    <b>NetEventQueryPower</b> event. After establishing an active connection, a
    protocol driver can call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff559731">PoRegisterSystemState</a> function to
    register a continuously busy state. As long as the state registration is in effect, the power manager
    does not attempt to put the system to sleep. After the connection becomes inactive, the protocol driver
    cancels the state registration by calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff559794">PoUnregisterSystemState</a> function. A
    protocol driver should never try to prevent the system from transitioning to the sleeping state by
    failing a 
    <b>NetEventQueryPower</b> event. Note that a 
    <b>NetEventQueryPower</b> event is always followed by a 
    <b>NetEventSetPower</b> event. A 
    <b>NetEventSetPower</b> event that specifies the underlying device's current power
    state in effect cancels the 
    <b>NetEventQueryPower</b> event.</p>

<p>If a protocol driver cannot release a device (for example, because the device is in use) it must fail
    a 
    <b>NetEventQueryRemoveDevice</b> event by returning NDIS_STATUS_FAILURE.</p>

<p>A protocol driver should always succeed a 
    <b>NetEventCancelRemoveDevice</b>, a 
    <b>NetEventReconfigure</b>, 
    <b>NetEventBindList, NetEventBindsComplete</b>, 
    <b>NetEventPnPCapabilities</b>, 
    <b>NetEventPause</b>, or 
    <b>NetEventPortDeactivation</b> by returning NDIS_STATUS_SUCCESS.</p>

<p>When handling a 
    <b>NetEventReconfigure</b> or a 
    <b>NetEventBindList</b>, a protocol driver should validate the data associated
    with the event. For more information about such data, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568752">NET_PNP_EVENT_NOTIFICATION</a>.</p>

<p>NDIS calls 
    <i>ProtocolNetPnPEvent</i> at IRQL = PASSIVE_LEVEL.</p>

<p>To define a <i>ProtocolNetPnPEvent</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>ProtocolNetPnPEvent</i> function that is named "MyNetPnPEvent", use the <b>PROTOCOL_NET_PNP_EVENT</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>PROTOCOL_NET_PNP_EVENT</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_NET_PNP_EVENT</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. </p>

<p>The 
    <i>ProtocolNetPnPEvent</i> function is required in protocol drivers to support Plug
    and Play and Power Management. NDIS calls 
    <i>ProtocolNetPnPEvent</i> to notify a protocol driver that a network Plug and Play
    event, an NDIS PnP event, or Power Management event has occurred.</p>

<p>The 
    <a href="https://msdn.microsoft.com/58d3baf3-a1fa-42ae-b795-2774a148aeda">
    NET_PNP_EVENT_NOTIFICATION</a> structure that is passed to 
    <i>ProtocolNetPnPEvent</i> describes the event. 
    <i>ProtocolNetPnPEvent</i> interprets two basic pieces of information in the
    NET_PNP_EVENT_NOTIFICATION structure:</p>

<p>A code in the 
      <b>NetEvent</b> member that identifies the type of Plug and Play or Power
      Management event.</p>

<p>Event-specific information. For example, with a 
      <b>NetEventSetPower</b> event the 
      <b>Buffer</b> member contains the device power state to which the device is
      transitioning.</p>

<p>The protocol driver should save the 
    <i>NetPnPEvent</i> pointer. This pointer is a required input parameter to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561705">NdisCompleteNetPnPEvent</a> function,
    which the protocol driver must subsequently call if 
    <i>ProtocolNetPnPEvent</i> returns NDIS_STATUS_PENDING.</p>

<p>A protocol driver should always succeed a 
    <b>NetEventQueryPower</b> event. After establishing an active connection, a
    protocol driver can call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff559731">PoRegisterSystemState</a> function to
    register a continuously busy state. As long as the state registration is in effect, the power manager
    does not attempt to put the system to sleep. After the connection becomes inactive, the protocol driver
    cancels the state registration by calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff559794">PoUnregisterSystemState</a> function. A
    protocol driver should never try to prevent the system from transitioning to the sleeping state by
    failing a 
    <b>NetEventQueryPower</b> event. Note that a 
    <b>NetEventQueryPower</b> event is always followed by a 
    <b>NetEventSetPower</b> event. A 
    <b>NetEventSetPower</b> event that specifies the underlying device's current power
    state in effect cancels the 
    <b>NetEventQueryPower</b> event.</p>

<p>If a protocol driver cannot release a device (for example, because the device is in use) it must fail
    a 
    <b>NetEventQueryRemoveDevice</b> event by returning NDIS_STATUS_FAILURE.</p>

<p>A protocol driver should always succeed a 
    <b>NetEventCancelRemoveDevice</b>, a 
    <b>NetEventReconfigure</b>, 
    <b>NetEventBindList, NetEventBindsComplete</b>, 
    <b>NetEventPnPCapabilities</b>, 
    <b>NetEventPause</b>, or 
    <b>NetEventPortDeactivation</b> by returning NDIS_STATUS_SUCCESS.</p>

<p>When handling a 
    <b>NetEventReconfigure</b> or a 
    <b>NetEventBindList</b>, a protocol driver should validate the data associated
    with the event. For more information about such data, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568752">NET_PNP_EVENT_NOTIFICATION</a>.</p>

<p>NDIS calls 
    <i>ProtocolNetPnPEvent</i> at IRQL = PASSIVE_LEVEL.</p>

<p>To define a <i>ProtocolNetPnPEvent</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>ProtocolNetPnPEvent</i> function that is named "MyNetPnPEvent", use the <b>PROTOCOL_NET_PNP_EVENT</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>PROTOCOL_NET_PNP_EVENT</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_NET_PNP_EVENT</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568752">NET_PNP_EVENT_NOTIFICATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561705">NdisCompleteNetPnPEvent</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559731">PoRegisterSystemState</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559794">PoUnregisterSystemState</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_NET_PNP_EVENT callback function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
