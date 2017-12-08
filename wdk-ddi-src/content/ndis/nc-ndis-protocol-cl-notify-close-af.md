---
UID: NC.ndis.PROTOCOL_CL_NOTIFY_CLOSE_AF
title: PROTOCOL_CL_NOTIFY_CLOSE_AF
author: windows-driver-content
description: The ProtocolClNotifyCloseAf function notifies a CoNDIS client that the client should close the associated address family (AF).Note  You must declare the function by using the PROTOCOL_CL_NOTIFY_CLOSE_AF type.
old-location: netvista\protocolclnotifycloseaf.htm
old-project: netvista
ms.assetid: 0f595daa-9822-4ca6-8f25-e6f82030d4ea
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolClNotifyCloseAf
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

# PROTOCOL_CL_NOTIFY_CLOSE_AF callback



## -description
<p>The 
  <i>ProtocolClNotifyCloseAf</i> function
  notifies a CoNDIS client that the client should close the associated address family (AF).</p>


## -prototype

````
PROTOCOL_CL_NOTIFY_CLOSE_AF ProtocolClNotifyCloseAf;

NDIS_STATUS ProtocolClNotifyCloseAf(
  _In_ NDIS_HANDLE ProtocolAfContext
)
{ ... }
````


## -parameters
<dl>

### -param ProtocolAfContext [in]

<dd>
<p>A client-supplied handle to its context area for the associated AF. The client allocated this
     context area and passed this handle to NDIS in its call to the 
     <a href="..\ndis\nf-ndis-ndisclopenaddressfamilyex.md">
     NdisClOpenAddressFamilyEx</a> function.</p>
</dd>
</dl>

## -returns
<p><i>ProtocolClNotifyCloseAf</i> can
     return one of the following:</p><dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><p>The client successfully closed the address family.</p><dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl><p>The client is handling this request asynchronously, and it will call the 
       <a href="..\ndis\nf-ndis-ndisclnotifycloseaddressfamilycomplete.md">
       NdisClNotifyCloseAddressFamilyComplete</a> function when the close operation is complete.</p><dl>
<dt><b>NDIS_STATUS_<i>XXX</i></b></dt>
</dl><p>The client failed the request for some driver-determined reason.</p>

<p> </p>

## -remarks
<p>The 
    <i>
    ProtocolClNotifyCloseAf</i> function is required for CoNDIS clients. NDIS calls 
    <i>ProtocolClNotifyCloseAf</i> when a
    call manager notifies NDIS that the address family (AF) that the 
    <i>ProtocolAfContext</i> parameter specifies should be closed. In response, the client
    should:</p>

<p>Call the 
      <a href="..\ndis\nf-ndis-ndiscldropparty.md">NdisClDropParty</a> function as many times
      as necessary until only a single party remains active on each multipoint virtual connection (VC), if
      the client has any active multipoint connections.</p>

<p>Call the 
      <a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a> function as many times
      as necessary to close all of the calls that are still open and are associated with the AF.</p>

<p>Call the 
      <a href="..\ndis\nf-ndis-ndisclderegistersap.md">NdisClDeregisterSap</a> function as many
      times as necessary to deregister all service access points (SAPs) that the client has registered with
      the call manager.</p>

<p>Call the 
      <a href="..\ndis\nf-ndis-ndisclcloseaddressfamily.md">
      NdisClCloseAddressFamily</a> function to close the AF.</p>

<p>The client can complete these actions asynchronously by returning NDIS_STATUS_PENDING. If the client
    completes the call asynchronously, it must subsequently call the 
    <a href="..\ndis\nf-ndis-ndisclnotifycloseaddressfamilycomplete.md">
    NdisClNotifyCloseAddressFamilyComplete</a> function when the close operation is complete. If the client
    does not return NDIS_STATUS_PENDING, the close operation is complete when 
    <i>
    ProtocolClNotifyCloseAf</i> returns.</p>

<p>NDIS calls 
    <i>ProtocolClNotifyCloseAf</i> at IRQL
    &lt;= DISPATCH_LEVEL.</p>

<p>The client may use the 
    <i>NdisAfHandle</i> while the AF is open or while a 
    <i>
    ProtocolClNotifyCloseAf</i> operation is pending. If the 
    <i>
    ProtocolClNotifyCloseAf</i> function returns NDIS_STATUS_PENDING, use the handle in the 
    <a href="..\ndis\nf-ndis-ndisclnotifycloseaddressfamilycomplete.md">
    NdisClNotifyCloseAddressFamilyComplete</a> call after the close operation completes.</p>

<p>To define a <i>ProtocolClNotifyCloseAf</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>ProtocolClNotifyCloseAf</i> function that is named "MyClNotifyCloseAf", use the <b>PROTOCOL_CL_NOTIFY_CLOSE_AF</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>PROTOCOL_CL_NOTIFY_CLOSE_AF</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_NOTIFY_CLOSE_AF</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

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
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisclcloseaddressfamily.md">NdisClCloseAddressFamily</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisclnotifycloseaddressfamilycomplete.md">
   NdisClNotifyCloseAddressFamilyComplete</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisclderegistersap.md">NdisClDeregisterSap</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscldropparty.md">NdisClDropParty</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisclopenaddressfamilyex.md">NdisClOpenAddressFamilyEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CL_NOTIFY_CLOSE_AF callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
