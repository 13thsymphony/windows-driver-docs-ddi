---
UID: NC.ndis.MINIPORT_CO_ACTIVATE_VC
title: MINIPORT_CO_ACTIVATE_VC
author: windows-driver-content
description: The MiniportCoActivateVc function is required for connection-oriented miniports.
old-location: netvista\miniportcoactivatevc.htm
old-project: netvista
ms.assetid: 243a1236-4b8a-4f00-9f14-3142fa81c362
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    MiniportCoActivateVc (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    MiniportCoActivateVc (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MiniportCoActivateVc
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
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# MINIPORT_CO_ACTIVATE_VC callback



## -description
<p>The 
  <i>MiniportCoActivateVc</i> function is required for connection-oriented miniports. 
  <i>MiniportCoActivateVc</i> is called by NDIS to indicate to the miniport driver that a
  virtual connection is being activated.</p>


## -prototype

````
MINIPORT_CO_ACTIVATE_VC MiniportCoActivateVc;

NDIS_STATUS MiniportCoActivateVc(
  _In_    NDIS_HANDLE         MiniportVcContext,
  _Inout_ PCO_CALL_PARAMETERS CallParameters
)
{ ... }
````


## -parameters
<dl>

### -param <i>MiniportVcContext</i> [in]

<dd>
<p>Specifies the handle to a miniport driver-allocated context area in which the miniport driver
     maintains its per-VC state. The miniport driver supplied this handle to NDIS from its 
     <i>MiniportCoCreateVc</i> function.</p>
</dd>

### -param <i>CallParameters</i> [in, out]

<dd>
<p>Specifies the call parameters, as specified by the call manager, to be established for this VC. On
     output, the miniport driver returns altered call parameters if certain flags are set in the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> structure.</p>
</dd>
</dl>

## -returns
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><p>Indicates that the VC was activated successfully.</p><dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl><p>Indicates that the miniport driver will complete the request to activate a VC asynchronously.
       When the miniport driver has finished with its operations, it must call 
       <a href="..\ndis\nf-ndis-ndismcoactivatevccomplete.md">
       NdisMCoActivateVcComplete</a>.</p><dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl><p>Indicates that the call parameters specified at 
       <i>CallParameters</i> are invalid or illegal for the media type that this miniport
       driver supports.</p><dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl><p>Indicates that the miniport driver could not activate the VC because it could not allocate all
       of the required resources that the miniport driver needs to maintain state information about the
       active VC.</p>

<p> </p>

## -remarks
<p>The miniport driver must validate the call parameters for this VC, as specified in 
    <i>CallParameters</i>, to verify that the adapter can support the requested call. If
    the requested call parameters cannot be satisfied, the miniport driver should fail the request with
    NDIS_STATUS_INVALID_DATA.</p>

<p><i>MiniportCoActivateVc</i> can be called many times for a single VC in order to
    change the call parameters for an already active call. At every call, the miniport driver should validate
    the parameters and perform any processing as required by its adapter in order to satisfy the request.
    However, if it cannot set the given call parameters, 
    <i>MiniportCoActivateVc</i> must leave the VC in a usable state, because the
    connection-oriented client or a call manager can continue to send or receive data using the older call
    parameters.</p>

<p>If the ROUND_UP_FLOW or ROUND_DOWN_FLOW flags are set in the call parameters structure at 
    <i>CallParameters-&gt;MediaParameters-&gt;Flags</i>, the miniport driver has been
    requested to return the actual flow rate of the VC after the flow rate has been rounded according to the
    appropriate flag that has been set. If the miniport driver does change any of the call parameters because
    these flags have been set, it must return the actual call parameters in use for the VC at 
    <i>CallParameters</i>.</p>

<p>If the call parameters are acceptable, 
    <i>MiniportCoActivateVc</i> communicates with its adapter as necessary to prepare the
    adapter to receive or transmit data across the virtual connection (in other words, programming receive
    buffers).</p>

<p>To define a <i>MiniportCoActivateVc</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>MiniportCoActivateVc</i> function that is named "MyCoActivateVc", use the <b>MINIPORT_CO_ACTIVATE_VC</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>MINIPORT_CO_ACTIVATE_VC</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_CO_ACTIVATE_VC</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/d7a61d90-3e53-4cc3-b89f-84e3e3a59fed">MiniportCoActivateVc (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <i>MiniportCoActivateVc (NDIS
   5.1)</i>) in Windows XP.</p>
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
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport-co-create-vc.md">MiniportCoCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-co-deactivate-vc.md">MiniportCoDeactivateVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcoactivatevccomplete.md">NdisMCoActivateVcComplete</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_CO_ACTIVATE_VC callback function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
